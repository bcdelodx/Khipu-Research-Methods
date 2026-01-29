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
            <h2>Access Full Framework Documentation</h2>
        </header>
        <p>
            Complete the form below to receive download access to KRL framework whitepapers.
            Your information helps us understand our research community and improve our work.
        </p>

        <!--
        =====================================================================
        INTEGRATION OPTIONS: Choose ONE of the following form implementations
        =====================================================================

        OPTION 1: MAILCHIMP
        - Create a signup form in Mailchimp Audience > Signup forms > Embedded forms
        - Copy the form HTML and paste below, replacing the placeholder
        - Set up an automation to send download links after signup
        - Use merge tags to track which framework was requested

        OPTION 2: HUBSPOT
        - Create a form in HubSpot Marketing > Forms
        - Include fields: Email, First Name, Last Name, Company, Framework Interest
        - Set up a workflow to send download links based on form submission
        - Use the embed code below, replacing YOUR_PORTAL_ID and YOUR_FORM_ID

        OPTION 3: FORMSPREE (Simple, no account needed for basic use)
        - The form below works with Formspree out of the box
        - Create account at formspree.io and get your form endpoint
        - Replace YOUR_FORMSPREE_ENDPOINT with your endpoint
        =====================================================================
        -->

        <!-- MAILCHIMP EMBED PLACEHOLDER -->
        <!--
        <div id="mc_embed_signup">
            Paste your Mailchimp embedded form code here
        </div>
        -->

        <!-- HUBSPOT EMBED PLACEHOLDER -->
        <!--
        <script charset="utf-8" type="text/javascript" src="//js.hsforms.net/forms/embed/v2.js"></script>
        <script>
            hbspt.forms.create({
                region: "na1",
                portalId: "YOUR_PORTAL_ID",
                formId: "YOUR_FORM_ID",
                redirectUrl: "{{ site.baseurl }}/download-confirm.html"
            });
        </script>
        -->

        <!-- DEFAULT FORM (Works with Formspree or can be adapted) -->
        <form id="framework-download-form" method="POST" action="https://formspree.io/f/YOUR_FORMSPREE_ENDPOINT">
            <div class="row uniform">
                <div class="6u 12u$(xsmall)">
                    <input type="text" name="first_name" id="first_name" placeholder="First Name" required />
                </div>
                <div class="6u$ 12u$(xsmall)">
                    <input type="text" name="last_name" id="last_name" placeholder="Last Name" required />
                </div>
                <div class="6u 12u$(xsmall)">
                    <input type="email" name="email" id="email" placeholder="Email Address" required />
                </div>
                <div class="6u$ 12u$(xsmall)">
                    <input type="text" name="organization" id="organization" placeholder="Organization (Optional)" />
                </div>
                <div class="12u$">
                    <div class="select-wrapper">
                        <select name="framework" id="framework" required>
                            <option value="">Select Framework Paper</option>
                            <option value="cge-abm">CGE-ABM Framework for Cultural-Economic Systems</option>
                            <!-- Add more frameworks as they become available -->
                        </select>
                    </div>
                </div>
                <div class="12u$">
                    <div class="select-wrapper">
                        <select name="use_case" id="use_case">
                            <option value="">How do you plan to use this research? (Optional)</option>
                            <option value="academic">Academic Research</option>
                            <option value="policy">Policy Analysis</option>
                            <option value="education">Educational Purposes</option>
                            <option value="professional">Professional/Consulting</option>
                            <option value="personal">Personal Interest</option>
                            <option value="other">Other</option>
                        </select>
                    </div>
                </div>
                <div class="12u$">
                    <ul class="actions">
                        <li><input type="submit" value="Request Download Access" class="special" /></li>
                    </ul>
                </div>
            </div>

            <!-- Hidden field to track source -->
            <input type="hidden" name="_subject" value="KRL Framework Download Request" />
            <input type="hidden" name="_next" value="{{ site.url }}{{ site.baseurl }}/download-confirm.html" />
        </form>

        <hr class="major" />

        <h3>What You'll Receive</h3>
        <p>
            Upon registration, you'll receive access to the complete whitepaper documentation including:
        </p>
        <ul>
            <li>Full technical methodology and system architecture</li>
            <li>Data sources, assumptions, and validation protocols</li>
            <li>Scenario templates and implementation guidance</li>
            <li>Governance frameworks and ethical considerations</li>
            <li>Updates when new versions are released</li>
        </ul>

        <h3>Privacy</h3>
        <p>
            Your information is used solely to provide research access and occasional updates about KRL frameworks.
            We do not sell or share your data with third parties. You may unsubscribe at any time.
        </p>
    </div>
</section>
