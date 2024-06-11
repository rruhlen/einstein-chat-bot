<script type='text/javascript'>
	function initEmbeddedMessaging() {
		try {
			// Retrieve user information from sessionStorage
			let userInfo = sessionStorage.getItem('user');
			let botSettings = {
				language: 'en_US' // For example, enter 'en' or 'en-US'
			};

			// If user information exists, add it to the bot settings
			if (userInfo) {
				userInfo = JSON.parse(userInfo);
				//botSettings.prechatUserName = userInfo.name;
				botSettings.prechatUserEmail = userInfo.username;
			}

			// Initialize the embedded service bootstrap with user information if available
			embeddedservice_bootstrap.settings.language = botSettings.language;

			// You may need to customize these settings further based on your requirements
			embeddedservice_bootstrap.settings.extraPrechatFormDetails = [
				//{ label: 'Name', value: botSettings.prechatUserName, transcriptFields: ['Name__c'] },
				{ label: 'Email', value: botSettings.prechatUserEmail, transcriptFields: ['Email__c'] }
			];

			embeddedservice_bootstrap.init(
				'00DHr000003YflM',
				'Vrtly_Chat_Bot',
				'https://vrtly.my.site.com/ESWVrtlyChatBot1717109571998',
				{
					scrt2URL: 'https://vrtly.my.salesforce-scrt.com'
				}
			);
		} catch (err) {
			console.error('Error loading Embedded Messaging: ', err);
		}
	};
</script>
<script type='text/javascript' src='https://vrtly.my.site.com/ESWVrtlyChatBot1717109571998/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>
