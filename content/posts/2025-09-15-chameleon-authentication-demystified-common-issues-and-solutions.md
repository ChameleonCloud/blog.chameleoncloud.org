---
abstract: <p>Don't let authentication problems derail your research momentum. This
  practical guide demystifies Chameleon's login system and arms you with clear, step-by-step
  solutions for the authentication challenges that frustrate users most. Learn to
  confidently navigate multiple accounts, identity provider changes, and stubborn
  login issues.</p>
authors:
- Paul Marshall
categories:
- Tips and Tricks
date: '2025-09-15 18:02:30+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/f3/77/f377c6f9-de57-45ff-9487-12224af93f28/head.jpg
related_posts:
- slug: chameleon-changelog-for-august-2025
  title: Chameleon Changelog for August 2025
- slug: experiment-pattern-bastion-host
  title: 'Experiment Pattern: Bastion Host'
- slug: chameleon-access-federated-login-coming-soon
  title: Chameleon Access via Federated Login Coming Soon!
slug: chameleon-authentication-demystified-common-issues-and-solutions
subtitle: Navigating Federated Identity, Multiple Accounts, and Common Pitfalls
title: 'Chameleon Authentication Demystified: Common Issues and Solutions'
---

<p>Don't let authentication problems derail your research momentum. This practical guide demystifies Chameleon's login system and arms you with clear, step-by-step solutions for the authentication challenges that frustrate users most. Learn to confidently navigate multiple accounts, identity provider changes, and stubborn login issues.</p>

<p><img src="https://chameleoncloud.org/media/filer_public/f3/77/f377c6f9-de57-45ff-9487-12224af93f28/head.jpg"></p>

<p><em>Photo by Markus Spiske on Unsplash</em></p>

<h3>Account Basics</h3>

<p>Getting started with Chameleon is straightforward thanks to our federated authentication system through Globus. Most users can sign in using credentials they already have through their institution—no need to create yet another username and password.</p>

<p>When you visit Chameleon and click "Sign in via federated login," you'll be redirected to Globus where you can select your institution (or another identity provider like GitHub or Google) to authenticate. Once authenticated, Globus maps your account to a unique Chameleon account, and you're ready to go.</p>

<p><strong>Important:</strong> If you previously used TACC federated identity to access Chameleon, note that this authentication method has been deprecated and will no longer be available as of January 2026. Please follow the steps outlined in <a href="#">our changelog</a> to migrate your account to Globus authentication.</p>

<p>For detailed guidance on account setup, getting allocations, adding users to projects, and understanding day passes and anonymous access options, see <a href="#">our comprehensive user documentation</a>.</p>

<h3>Technical Details</h3>

<p>Under the hood, Chameleon auth is federated with Globus. What this means practically is that when you login to Chameleon, you are actually redirected to Globus where you can select an identity provider, such as your institution (or Globus itself as an identity provider if you have a Globus account), and login.</p>

<p><img src="https://chameleoncloud.org/media/filer_public/3a/82/3a825955-6c7c-492e-aa66-2db45701d4e9/globus.png"></p>

<p>The Globus login flow after clicking "Sign in via federated login:"</p>

<p>Once authenticated through Globus (and possibly your institution or another valid identity provider, such as GitHub or Google) your Globus account is mapped to a unique account on Chameleon. Chameleon doesn't manage your underlying account with your password at all!</p>

<p>After successful login via Globus, Chameleon creates an authenticated session for you, which grants you access to certain portions of Chameleon based on your permissions.</p>

<h3>Managing Multiple Accounts &amp; Identity Changes</h3>

<p>Users sometimes find themselves with multiple accounts or need to change their primary login method. Here are the most common scenarios and solutions:</p>

<h4>Multiple Institutional Accounts</h4>

<p>If you have accounts at different institutions and need access to the same Chameleon projects, account merging is typically not necessary. Instead, the recommended approach is to have your project PI add your additional account to the existing project. This grants access without requiring complex backend changes.</p>

<p>For example, if you started a project using your university email but now need access from a different institution, simply ask your project administrator to add your new institutional account to the project rather than attempting to merge accounts.</p>

<h4>Changing Your Primary Identity Provider</h4>

<p>If you've switched your primary GitHub/Google account or changed institutions and want to update your Chameleon login method, you can manage this through your Globus account settings:</p>

<ol>
	<li>Visit your <a href="#">Globus identity settings</a></li>
	<li>Link your new identity provider (GitHub, new institution, etc.)</li>
	<li>Set it as your primary identity if the option is available</li>
	<li>Clear your browser cache and reauthenticate via Chameleon's federated login</li>
</ol>

<p>To verify which identity provider you're currently using, check your Globus identity settings page—your primary identity will be clearly marked, and you can see all linked accounts.</p>

<p>If you cannot change your primary identity through the Globus web interface, contact Globus support directly for assistance.</p>

<h4>When You Can't Access Your Account</h4>

<p>If you're having trouble accessing projects you should have permission for, first verify you're logging in through the correct identity provider. It's easy to accidentally sign in through a different account than the one linked to your Chameleon projects.</p>

<h3>Common Pitfalls</h3>

<p>Federation for auth can be a point of confusion for many. It comes with a few key caveats worth calling out:</p>

<ol>
	<li><strong>Chameleon doesn't store your password.</strong> Because Chameleon federates auth, we don't have your password and can't ever reset it if you forget it. For that you need to contact your identity provider, such as your home institution, to help reset and manage your credentials.</li>
	<li><strong>Stale cookies.</strong> Federated auth relies on cookies to manage your login state and these cookies can become out-of-sync, stale, or corrupt, which can prevent login. The easiest solution is to just clear your cookies and login again or try logging into Chameleon with a different browser whenever the login flow isn't working correctly. More often than not this resolves cookie-related issues.</li>
	<li><strong>Using the wrong account.</strong> Users sometimes have multiple accounts that they've used with Chameleon and they forget to sign in their Globus-linked account through their institution. If you are having trouble logging in make sure you are following the Globus auth flow and signing in through your institution or another Globus-supported identity provider.</li>
	<li><strong>Identity provider confusion.</strong> When switching between different identity providers (like moving from one GitHub account to another), make sure you're managing the change through your Globus account settings first, then clear your browser cache before attempting to sign in to Chameleon.</li>
</ol>

<h3>Need Help?</h3>

<p>If you're experiencing authentication issues that aren't resolved by the troubleshooting steps above, our support team is here to help. Most account-related issues can be resolved quickly with the right guidance from our <a href="http://chameleoncloud.org/help">help desk</a>.</p>

<p><strong>Remember:</strong> for password resets and primary account management, you'll need to work with your identity provider (your institution or Globus directly). For project access and Chameleon-specific permissions, our support team can assist you or connect you with the right project administrators.</p>

<p>The key to smooth authentication with Chameleon is understanding that we leverage the accounts you already have—making it easier for you to get started with your research without managing another set of credentials.</p>