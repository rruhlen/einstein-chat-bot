<script type='text/javascript'>
	function initEmbeddedMessaging() {
		try {
			// Wait for Embedded Messaging to be ready
			window.addEventListener('onEmbeddedMessagingReady', function(e) {
				embeddedservice_bootstrap.settings.language = 'en_US'; // Set language
				
				// Check if sessionStorage.user exists
				if (sessionStorage.user) {
					// Parse the user data from sessionStorage
					const user = JSON.parse(sessionStorage.user);
					
					// Extract the required fields
					const userName = user.name || '';
					const userEmail = user.organization ? user.organization.email : '';
					const organizationId = user.organization ? user.organization.id : '';

					// Split full name into first name and last name
					let [firstName, ...lastNameParts] = fullName.split(' ');
					let lastName = lastNameParts.join(' ') || ''; // Join remaining parts as last name (in case of multi-part last names)

					// Set hidden pre-chat fields with extracted values
					embeddedservice_bootstrap.setHiddenPrechatFields({
						_FirstName: firstName,
						_LastName: lastName,
						_Email: userEmail,
						Practice_ID: organizationId
					});
				} else {
					console.warn('sessionStorage.user not found');
				}
			});

			// Initialize Embedded Messaging
			embeddedservice_bootstrap.init(
				'00DHr000003YflM',
				'New_Vrtly_Chat_Bot_for_GitHub',
				'https://vrtly.my.site.com/ESWNewVrtlyChatBotfor1727235927198',
				{
					scrt2URL: 'https://vrtly.my.salesforce-scrt.com'
				}
			);
		} catch (err) {
			console.error('Error loading Embedded Messaging: ', err);
		}
	};
</script>

<!-- Include Bootstrap and load Embedded Messaging -->
<script type='text/javascript' src='https://vrtly.my.site.com/ESWNewVrtlyChatBotfor1727235927198/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>

<!-- Example Pre-chat Form -->
<form id="pre-chat-form" style="display:none;">
	<input type="hidden" id="prechat-name-field" name="Name" />
	<input type="hidden" id="prechat-email-field" name="Email" />
	<input type="hidden" id="prechat-org-id-field" name="OrganizationId" />
</form>
