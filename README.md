1. **Draft Linked API** \
    [Example](/json-schemas/linked-apis/examples/example-linked-api-draft.json)
    -  `Publish mode` - Set this value to `Manual` in the portal. 
    -  `displayName` - This value must be between 3 and 100 characters.
    -  `description` - This value must not exceed 40 characters.
    -  `backendType` - There are three available options - `http` (rest) ,`soap`, and `graphql`. If a different option is given, the specification will fail on validation.
    -  `majorVersion` - This value must not exceed the 50 character limit, e.g. 'v1'.
    -  `environments` - They are not required for this scenario, therefore the object is left empty.
    - `siteUrl` - This value must not exceed 200 characters 

2. **Draft Linked Api + Metadata and Environments** \
      [Example](/json-schemas/linked-apis/examples/example-linked-api-draft-with-metadata.json) \
    All of the above are required in this section. The following are also needed:
    -  `overview`: A friendly message that will be presented to the users in the Consumption portal.
    -  `classification` - allowed values -  `Public facing`, `Across government services`, `Across departmental services`, `Within service boundary`.
    -  `visibility` - Allowed values are `Public`, `Internal`, `Private`.
    -  `tags` - words that are separated by semi-colon. They are used to utilize the search of APIs in FaUAPI.
    -  `serviceLevel` - The level of service can be specified here as a short description.
    -  `technology` - what technology is used for the development of the API.
    - `usage` - Describe who can use this API.
    - `environments` - Allows to have 0 or max 3 environments, with unique names - `live`, `staging` or `dev`.

3. **Auto Publish Linked API** \
 [Example](/json-schemas/linked-apis/examples/example-linked-api-publish.json) \
    All the properties from section 1 and 2 are required here as well.
   - `Publish mode` - Set this value to `Automatic` in the portal. . This will require more properties to be added to validate the specification.
   - `schemaURL` - A valid url of where the schema of the api is located.
   - `schemaType` - The type of the schema. Valid values are `openapi`,`wsdl`,`swagger`.
   - `releases` - At least one release is required. `isCurrent` flag must be set to `true`, otherwise the specification will not validate. The tag must
   be one of the following : `Planned` , `Alpha` , `Beta` , `Live` , `Deprecated` .