<script>
	import { themes } from '$lib/config.js';
	import { getContext } from 'svelte';
	import ONSLogo from './ONSLogo.svelte';

	export let theme = getContext('theme');

	let colors = theme ? themes[theme] : {};
	let primary = theme == 'dark' ? 'white' : '#222222';
	let secondary = theme == 'dark' ? '#a8bd3a' : '#222222';
</script>

<footer
	style:--text={colors.text}
	style:--background={colors.background}
	style:--muted={colors.muted}
	style:--pale={colors.pale}
>
	<div class="col-wide" data-analytics="footer">
		<a href="https://www.ons.gov.uk/">
			<div class="logo-img">
				<ONSLogo {primary} {secondary} />
			</div>
		</a>
		<ul>
			<li><a href="https://www.ons.gov.uk/aboutus/contactus" class="link">Contact us</a></li>
			<li>
				<a href="https://www.ons.gov.uk/help/privacynotice" class="link">Cookies and privacy</a>
			</li>
		</ul>
		<hr />
		<div class="license">
			<svg class="ogl-img" viewBox="0 0 59 24" xmlns="http://www.w3.org/2000/svg">
				<title>UK Open Government Licence</title>
				<path
					d="M59,17.5v6.2H45.3V4l6.2-3.9v17.4H59z M33.6,13h9.8v10.7H43L40.6,21c-2.1,1.8-4.9,3-7.9,3 c-4.4,0-8.3-2.4-10.4-6.1c-2.1,3.6-5.9,6.1-10.4,6.1C5.4,23.9,0,18.6,0,12C0,5.4,5.4,0.1,11.9,0.1c4.5,0,8.4,2.5,10.4,6.1 c2.1-3.6,5.9-6.1,10.4-6.1c4.2,0,7.9,2.2,10.1,5.5l-5.2,3.3c-1-1.6-2.8-2.7-4.8-2.7C29.6,6.2,27,8.8,27,12s2.6,5.8,5.8,5.8 c1.5,0,2.8-0.5,3.8-1.4L33.6,13z M17.7,12c0-3.2-2.6-5.7-5.8-5.7S6.2,8.8,6.2,12s2.6,5.8,5.8,5.8S17.7,15.2,17.7,12z"
				/>
			</svg>
			All content is available under the
			<a
				href="https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/"
				class="link"
				target="_blank"
				rel="noopener">Open Government Licence v3.0</a
			>, except where otherwise stated
		</div>
	</div>
</footer>

<style>
	footer {
		padding-bottom: 72px;
		padding-top: 36px;
		font-size: 18px;
		color: var(--text, #222);
		background-color: var(--pale, #f0f0f0);
	}
	footer a.link {
		-webkit-box-sizing: border-box;
		box-sizing: border-box;
		text-decoration: underline;
		display: inline-block;
		color: var(--text, #222);
	}
	footer a.link:hover {
		text-decoration: none;
	}
	footer a.link:active {
		outline: 3px solid transparent;
		background-color: #fd0;
		-webkit-box-shadow:
			0 -2px #fd0,
			0 4px #222;
		box-shadow:
			0 -2px #fd0,
			0 4px #222;
		color: #222;
		text-decoration: none;
	}
	footer hr {
		margin-bottom: 27px;
		margin-top: 36px;
		border: none;
		border-top: 1px solid var(--muted, #777);
	}
	footer svg > path {
		fill: var(--muted, #777);
	}
	ul {
		padding: 0;
		margin: 0;
	}
	li {
		margin-right: 18px;
		display: inline-block;
	}
	.logo-img {
		width: 205px;
		margin-bottom: 27px;
	}
	.ogl-img {
		margin: 0 0.5rem 0.2rem 0;
		width: 59px;
		height: 24px;
		vertical-align: middle;
	}
	.license {
		vertical-align: top;
	}
	a .logo-img:hover {
		cursor: pointer;
	}
</style>
