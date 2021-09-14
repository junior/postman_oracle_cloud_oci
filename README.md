# Oracle Cloud Infrastructure REST APIs

Here you will find Information to use Oracle Cloud Infrastructure REST APIs with Postman

The Oracle Cloud Infrastructure APIs are typical REST APIs that use HTTPS requests and responses.

## Using the Collections to make API calls

### Get OCI Credentials

- **tenancy_ocid**: OCID of your tenancy.
    To get the value, see [Required Keys and OCIDs](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/apisigningkey.htm#Required_Keys_and_OCIDs).
    Example: `ocid1.tenancy.oc1..<unique_ID>` (shortened for brevity)

- **user_ocid**: OCID of the user calling the API. 
    To get the value, see [Required Keys and OCIDs](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/apisigningkey.htm#Required_Keys_and_OCIDs).
    Example: `ocid1.user.oc1..<unique_ID>`

- **fingerprint**: Fingerprint for the public key that was added to this user.
    To get the value, see [Required Keys and OCIDs](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/apisigningkey.htm#Required_Keys_and_OCIDs).

- **private_key**: Contents of the private key file. 
    You can open the file in an editor and copy the contents or use a command like `pbcopy < ~/.oci/oci_api_key.pem` 
    The key pair must be in PEM format. For instructions on generating a key pair in PEM format, see [Required Keys and OCIDs](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/apisigningkey.htm#Required_Keys_and_OCIDs).

- **passphrase**: Passphrase used for the key. Only required if it key is encrypted.

- **region**: An Oracle Cloud Infrastructure region. See [Regions and Availability Domains](https://docs.oracle.com/en-us/iaas/Content/General/Concepts/regions.htm#top).
    Example: `us-ashburn-1`

- **compartment_ocid**: OCID of the compartment that will be used for the API calls.

## API Reference and Endpoints

For links to the Oracle Cloud Infrastructure API reference and a list of the regional API endpoints, see [API Reference and Endpoints](https://docs.oracle.com/iaas/api/).

## API Version

The base path of the endpoint includes the desired API version (for example, 20160918). Here's an example for a POST request to create a new VCN in the Ashburn region:

```bash
POST https://iaas.us-ashburn-1.oraclecloud.com/20160918/vcns
```

## API Breaking Changes Policy

Oracle Cloud Infrastructure will provide 12 months advance notice prior to the date of removing or changing an existing API of a Cloud Service that you have deployed which would require you to update your code.

## Maximum Allowed Client Clock Skew

HTTP status code 401 (NotAuthenticated) is returned if the client's clock is skewed more than 5 minutes from the server's. 

## Request and Response Format

The Oracle Cloud Infrastructure APIs use standard HTTP requests and responses. Each may contain Oracle-specific headers for pagination, entity tags (ETags), and so on as described elsewhere in this topic and in the API documentation.

Each response includes a unique Oracle-assigned request ID (for example, bb3f3275-f356-462a-93c4-bf40fb82bb02) in the `opc-request-id` response header. If you need to contact Oracle about a particular request, please provide this request ID.

Many of the API operations require JSON in the request body or return JSON in the response body. The specific contents of the JSON are described in the API documentation for the individual operation. Notice that the JSON is not wrapped or labeled according to the operation's name or the object's name or type.

> Note: Make sure to set the Content-Type header to application/json in your POST and PUT requests that contain JSON in the body.
