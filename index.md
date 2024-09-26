<script type='text/javascript'>
	function initEmbeddedMessaging() {
		try {
			// Set language
			embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'

			// Wait for Embedded Messaging to be ready
			window.addEventListener('onEmbeddedMessagingReady', function(e) {
				// Check if sessionStorage.user exists
				if (sessionStorage.user) {
					// Parse the user data from sessionStorage
					const user = JSON.parse(sessionStorage.user);
					
					// Extract the required fields
					const fullName = user.name || '';
					const userEmail = user.organization ? user.organization.email : '';
					const practiceId = user.organization ? user.organization.id : ''; // Practice ID

					// Split full name into first name and last name
					let [firstName, ...lastNameParts] = fullName.split(' ');
					let lastName = lastNameParts.join(' ') || ''; // Handle multi-part last names

					// Set hidden pre-chat fields with extracted values
					embeddedservice_bootstrap.setHiddenPrechatFields({
						_FirstName: firstName,  // Custom API name for first name
						_LastName: lastName,    // Custom API name for last name
						_Email: userEmail,
						Practice_ID: practiceId // Custom API name for Practice ID
					});
				} else {
					console.warn('sessionStorage.user not found');
				}
			});

			// Initialize Embedded Messaging
			embeddedservice_bootstrap.init(
				'00DHr000003YflM',
				'Another_test_for_rruhlen_github_io',
				'https://vrtly.my.site.com/ESWAnothertestforrruhl1727371215699',
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
<script type='text/javascript' src='https://vrtly.my.site.com/ESWAnothertestforrruhl1727371215699/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>

<!-- Example Pre-chat Form (if needed) -->
<form id="pre-chat-form" style="display:none;">
	<input type="hidden" id="prechat-firstname-field" name="_FirstName" />
	<input type="hidden" id="prechat-lastname-field" name="_LastName" />
	<input type="hidden" id="prechat-email-field" name="_Email" />
	<input type="hidden" id="prechat-practiceid-field" name="Practice_ID" />
</form>
