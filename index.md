<script type='text/javascript'>
	function initEmbeddedMessaging() {
	try {
		window.addEventListener('onEmbeddedMessagingReady', function(e) {
			embeddedservice_bootstrap.settings.language = 'en_US'; // Set language
			
			// Set hidden pre-chat fields
			embeddedservice_bootstrap.setHiddenPrechatFields({
				Email: 'ricky@vrtly.ai' // Replace with actual email value
			});
		});

		embeddedservice_bootstrap.init(
			'00DHr000003YflM',
			'Vrtly_Testing_on_GitHub',
			'https://vrtly.my.site.com/ESWVrtlyTestingonGitHu1716919615212',
			{
				scrt2URL: 'https://vrtly.my.salesforce-scrt.com'
			}
		);
	} catch (err) {
		console.error('Error loading Embedded Messaging: ', err);
	}
};
alert("hey!!!");
</script>
<script type='text/javascript' src='https://vrtly.my.site.com/ESWVrtlyTestingonGitHu1716919615212/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>
