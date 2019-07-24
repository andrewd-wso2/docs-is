# Writing a XACML Policy using a Policy Template

This section guides you through using and editing the XACML policy
templates available in WSO2 Identity Server to write your own policy.

1.  Start WSO2 Identity Server and log in to the management console.
2.  Click on **Policy Administration** under the **Entitlement\>PAP**
    section on the **Main** tab.  
    ![](attachments/103331229/103331230.png){width="900"}
3.  You will see the following list of available policy templates.

    | Template Name                                                                                                                                                                              | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
    |--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | authn\_role\_based\_policy\_template                                                																									 | This policy template provides the abilitity to authorize users to a given service provider (defined by the `               SP_NAME              ` placeholder) in the authentication flow based on the roles of the user (defined by `               ROLE_1              ` and `               ROLE_2              ` placeholders). Users who have at least one of the given roles are permitted to log in and any others are denied.                                                                                                                                                                                                                                            |
    | authn\_scope\_based\_policy\_template                                               																									 | This template policy provides the ability to authorize users to a given service provider (defined by `               SP_NAME              ` placeholder) in the authentication flow based on the OAuth scope(s) ( `               SCOPE1, SCOPE2              ` ). Users who are authenticated with the given scopes are allowed and any other users are denied.                                                                                                                                                                                                                                                                                                                 |
    | authn\_time\_and\_role\_based\_policy\_template                           																												 | This policy template provides the ability to authorize users to a given service provider (defined by `               SP_NAME              ` placeholder) in the authentication flow based on the roles of the user (defined by `               ROLE_1              ` and `               ROLE_2              ` ) **and** the time of the day (e.g., between 09:00:00 to 17:00:00). Users who have at least one of the given roles are permitted to login within the given time. Any other requests will be denied.                                                                                                                                                               |
    | authn\_time\_and\_scope\_based\_policy\_template                          																												 | This template policy provides the ability to authorize users to a given service provider (defined by `               SP_NAME              ` placeholder) in the authentication flow based on the oauth scope(s) ( `               SCOPE1              ` or `               SCOPE2              ` ) and the time of the day (e.g., between 09:00:00 to 17:00:00). Users who are logging in between the given time and who grant the given scopes are permitted to login and any other user will be denied.                                                                                                                                                                        |
    | authn\_time\_and\_user\_claim\_based\_policy\_template               																													 | This template policy provides the ability to authorize users to a given service provider (defined by `               SP_NAME              ` placeholder) in the authentication flow based on the claim values of the user ( `               CLAIM_URI_1=CLAIM_VALUE_1              ` and `               CLAIM_URI_2=CLAIM_VALUE_2              ` ) and the time of the day (e.g., between 09:00:00 to 17:00:00). Users with the given claim values and who are logged in within the given time range are permitted and any other users will be denied.                                                                                                                          |
    | authn\_time\_based\_policy\_template                                                																									 | This template policy provides the ability to authorize users to a given service provider(defined by `               SP_NAME              ` placeholder) in the authentication flow based on the login time. Any authentication attempt outside the specified time range (09:00:00 to 17:00:00) will be denied.                                                                                                                                                                                                                                                                                                                                                                   |
    | provisioning\_role\_based\_policy\_template                                  																											 | This template policy provides the ability to authorize provisioning requests initiated from a given service provider (defined by `               SP_NAME              ` placeholder) to a given identity provider (defined by `               IDP_NAME              ` placeholder) in the outbound provisioning flow based on the roles of the user ( `               ROLE_1, ROLE_2              ` ). Provisioning attempts to the users with given role(s) are permitted and all others will be denied.                                                                                                                                                                        |
    | provisioning\_time\_and\_role\_based\_policy\_template              																													 | This template policy provides the ability to authorize provisioning requests initiated from a given service provider (defined by `               SP_NAME              ` placeholder) to a given identity provider (defined by `               IDP_NAME              ` placeholder) in the outbound provisioning flow based on the roles of the user ( `               ROLE_1, ROLE_2              ` ) and time of the day (e.g., between 09:00:00 to 17:00:00). Provisioning attempts to the users with given role(s) between the given time are permitted and all others will be denied.                                                                                        |
    | provisioning\_time\_and\_user\_claim\_based\_policy\_template 																															 | This template policy provides the ability to authorize provisioning requests initiated from a given service provider (defined by `               SP_NAME              ` placeholder) to a given identity provider(defined by `               IDP_NAME              ` placeholder) in the outbound provisioning flow based on the claim values of the user ( `               CLAIM_URI_1=CLAIM_VALUE_1              ` and `               CLAIM_URI_2=CLAIM_VALUE_2              ` ) and time of the day (e.g., between 09:00:00 to 17:00:00). Provisioning attempts to the users with the given claim values between the given time are permitted and all others will be denied. |
    | provisioning\_time\_based\_policy\_template                                  																											 | This template policy provides the ability to authorize provisioning requests initiated from a given service provider (defined by `               SP_NAME              ` placeholder) to a given identity provider(defined by `               IDP_NAME              ` placeholder) in the outbound provisioning flow based on the requested time. Any provisioning attempt outside the specified time range(09:00:00 to 17:00:00) will be denied.                                                                                                                                                                                                                                 |
    | provisioning\_user\_claim\_based\_policy\_template                     																													 | This template policy provides ability to authorize provisioning requests initiated from a given service provider (defined by `               SP_NAME              ` placeholder) to a given identity provider (defined by `               IDP_NAME              ` placeholder) in the outbound provisioning flow based on the claim values of the user ( `               CLAIM_URI_1=CLAIM_VALUE_1              ` and `               CLAIM_URI_2=CLAIM_VALUE_2              ` ). Users with the given claim values are permitted and any other users will be denied.                                                                                                            |

4.  Click the corresponding **Edit** button of the policy template that
    you want to use.
5.  Edit the **Policy ID** with a name relevant to your policy.
6.  Edit the placeholders with the relevant values and click **Save
    Policy**.  
    You can see the policy you just created on the policy list (the
    original template policy will remain unchanged for later use).
7.  Click on the **Publish to My PDP** link corresponding to the new
    policy.  
    ![publish-to-pdp](../../assets/img/tutorials/publish-to-pdp.png)
8.  On the UI that appears, leave the default selected values as they
    are and click **Publish**.  
    ![publishing-a-xacml-policy](../../assets/img/tutorials/publishing-a-xacml-policy.png)

    !!! note
    
        For more information on Publishing a XACML policy, click
        [here](../../tutorials/publishing-a-xacml-policy).
    

9.  Click on **Policy View** under the **Entitlement\>PDP** section on
    the **Main** tab of the management console.
10. To ensure that the policy has been published successfully, check if
    the policy is listed.
    ![check-policy-list](../../assets/img/tutorials/check-policy-list.png)