<html>
  <body>
    
<script type='text/javascript'>
	function initEmbeddedMessaging() {
		try {
			embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'

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
</script>
<script type='text/javascript' src='https://vrtly.my.site.com/ESWVrtlyTestingonGitHu1716919615212/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>


</body>
</html>
