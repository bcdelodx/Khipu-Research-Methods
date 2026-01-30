---
layout: page
title: Download Framework Papers
description: Register to access full whitepaper downloads
image: assets/images/pic11.jpg
nav-menu: false
show_tile: false
---

<!-- Registration Form Section -->
<section id="registration">
    <div class="inner">
        <header class="major">
            <h2>Get the Complete Technical Documentation</h2>
        </header>
        <p>
            Full whitepapers include detailed methodology, validation protocols, implementation guidance,
            and governance frameworks—everything needed to evaluate these tools for your research program.
        </p>

        <!-- Custom Styled Form - Submits to HubSpot -->
        <form id="framework-download-form">
            <div class="row uniform">
                <div class="6u 12u$(xsmall)">
                    <input type="text" name="firstname" id="firstname" placeholder="First Name" required />
                </div>
                <div class="6u$ 12u$(xsmall)">
                    <input type="text" name="lastname" id="lastname" placeholder="Last Name" required />
                </div>
                <div class="6u 12u$(xsmall)">
                    <input type="email" name="email" id="email" placeholder="Email Address" required />
                </div>
                <div class="6u$ 12u$(xsmall)">
                    <input type="tel" name="phone" id="phone" placeholder="Phone Number" />
                </div>
                <div class="6u 12u$(xsmall)">
                    <input type="text" name="city" id="city" placeholder="City" />
                </div>
                <div class="6u$ 12u$(xsmall)">
                    <input type="text" name="state" id="state" placeholder="State/Region" />
                </div>
                <div class="12u$">
                    <input type="text" name="company" id="company" placeholder="Organization (Optional)" />
                </div>
                <div class="12u$">
                    <div class="select-wrapper">
                        <select name="framework_interest" id="framework_interest" required>
                            <option value="">Select Framework Paper</option>
                            <option value="CGE-ABM Framework">CGE-ABM Framework for Cultural-Economic Systems</option>
                            <!-- Add more frameworks as they become available -->
                        </select>
                    </div>
                </div>
                <div class="12u$">
                    <div class="select-wrapper">
                        <select name="use_case" id="use_case">
                            <option value="">How do you plan to use this research? (Optional)</option>
                            <option value="Academic Research">Academic Research</option>
                            <option value="Policy Analysis">Policy Analysis</option>
                            <option value="Educational Purposes">Educational Purposes</option>
                            <option value="Professional/Consulting">Professional/Consulting</option>
                            <option value="Personal Interest">Personal Interest</option>
                            <option value="Other">Other</option>
                        </select>
                    </div>
                </div>
                <div class="12u$">
                    <ul class="actions">
                        <li><input type="submit" value="Request Download Access" class="special" id="submit-btn" /></li>
                    </ul>
                </div>
            </div>
        </form>

        <!-- Status message area -->
        <div id="form-status" style="display: none; padding: 1em; margin-top: 1em; border-radius: 4px;"></div>

        <hr class="major" />

        <h3>What's Inside</h3>
        <p>
            Each whitepaper provides the technical depth required for serious evaluation:
        </p>
        <ul>
            <li><strong>Complete methodology</strong> — Mathematical specifications, system architecture, and algorithmic details</li>
            <li><strong>Data documentation</strong> — Sources, assumptions, bias audits, and calibration protocols</li>
            <li><strong>Validation status</strong> — Current testing results, known limitations, and development roadmap</li>
            <li><strong>Implementation guidance</strong> — Scenario templates and configuration for your domain</li>
            <li><strong>Governance frameworks</strong> — Ethical considerations, appropriate use boundaries, and terms</li>
        </ul>
        <p>
            Registered users receive updates when new versions are released or validation milestones are reached.
        </p>

        <h3>Privacy</h3>
        <p>
            Your information is used solely to provide research access and occasional updates about KRL frameworks.
            We do not sell or share your data with third parties. You may unsubscribe at any time.
        </p>
    </div>
</section>

<!--
============================================================================
HUBSPOT INTEGRATION SETUP
============================================================================

To connect this form to HubSpot:

1. Create a HubSpot account (free CRM works) at https://www.hubspot.com

2. Create custom properties in HubSpot (Settings > Properties > Contact):
   - "framework_interest" (dropdown or single-line text)
   - "use_case" (dropdown or single-line text)

3. Create a form in HubSpot (Marketing > Forms):
   - Add fields: Email, First Name, Last Name, Company
   - Add your custom properties: framework_interest, use_case
   - Publish the form

4. Get your Portal ID and Form ID:
   - Portal ID: Settings > Account > Account Defaults (look for Hub ID)
   - Form ID: Shown in the form embed code after publishing

5. Replace the placeholders below:
   - YOUR_PORTAL_ID: Your HubSpot portal/hub ID (numbers only)
   - YOUR_FORM_ID: Your form GUID (xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx)

6. Optionally set up a workflow to email download links automatically

============================================================================
-->

<script>
document.getElementById('framework-download-form').addEventListener('submit', function(e) {
    e.preventDefault();

    // HubSpot Credentials
    var portalId = '244094806';
    var formId = 'e4692c23-82ba-479c-8063-e5558f7bceb3';

    var submitBtn = document.getElementById('submit-btn');
    var statusDiv = document.getElementById('form-status');

    // Disable button and show loading state
    submitBtn.disabled = true;
    submitBtn.value = 'Submitting...';

    // Collect form data
    var formData = {
        fields: [
            { name: 'email', value: document.getElementById('email').value },
            { name: 'firstname', value: document.getElementById('firstname').value },
            { name: 'lastname', value: document.getElementById('lastname').value },
            { name: 'phone', value: document.getElementById('phone').value },
            { name: 'city', value: document.getElementById('city').value },
            { name: 'state', value: document.getElementById('state').value },
            { name: 'company', value: document.getElementById('company').value },
            { name: 'framework_interest', value: document.getElementById('framework_interest').value },
            { name: 'use_case', value: document.getElementById('use_case').value }
        ],
        context: {
            pageUri: window.location.href,
            pageName: document.title
        }
    };

    // Submit to HubSpot Forms API
    fetch('https://api.hsforms.com/submissions/v3/integration/submit/' + portalId + '/' + formId, {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json'
        },
        body: JSON.stringify(formData)
    })
    .then(function(response) {
        if (response.ok) {
            // Success - redirect to download page
            window.location.href = '{{ site.baseurl }}/download-confirm.html';
        } else {
            return response.json().then(function(data) {
                throw new Error(data.message || 'Form submission failed');
            });
        }
    })
    .catch(function(error) {
        // Show error message
        statusDiv.style.display = 'block';
        statusDiv.style.backgroundColor = '#f8d7da';
        statusDiv.style.color = '#721c24';
        statusDiv.innerHTML = '<strong>Error:</strong> ' + error.message + '<br>Please try again or contact us directly.';

        // Re-enable button
        submitBtn.disabled = false;
        submitBtn.value = 'Request Download Access';
    });
});
</script>

<!--
============================================================================
ALTERNATIVE: MAILCHIMP INTEGRATION
============================================================================

If you prefer Mailchimp instead of HubSpot, replace the script above with:

1. Get your Mailchimp form action URL:
   - Go to Audience > Signup forms > Embedded forms
   - Look for the form action URL (starts with https://XXXX.us#.list-manage.com/subscribe/post)

2. Replace YOUR_MAILCHIMP_URL below and uncomment the script

<script>
document.getElementById('framework-download-form').addEventListener('submit', function(e) {
    e.preventDefault();

    var mailchimpUrl = 'YOUR_MAILCHIMP_URL'; // e.g., https://domain.us1.list-manage.com/subscribe/post?u=XXXX&id=XXXX

    var formData = new FormData();
    formData.append('EMAIL', document.getElementById('email').value);
    formData.append('FNAME', document.getElementById('firstname').value);
    formData.append('LNAME', document.getElementById('lastname').value);
    formData.append('COMPANY', document.getElementById('company').value);
    formData.append('FRAMEWORK', document.getElementById('framework_interest').value);
    formData.append('USECASE', document.getElementById('use_case').value);

    // Mailchimp requires JSONP or form submission, so we'll do a form submission
    var form = document.createElement('form');
    form.method = 'POST';
    form.action = mailchimpUrl;
    form.target = '_blank';

    for (var [key, value] of formData.entries()) {
        var input = document.createElement('input');
        input.type = 'hidden';
        input.name = key;
        input.value = value;
        form.appendChild(input);
    }

    document.body.appendChild(form);
    form.submit();

    // Redirect to download page
    setTimeout(function() {
        window.location.href = '{{ site.baseurl }}/download-confirm.html';
    }, 1000);
});
</script>

============================================================================
-->
