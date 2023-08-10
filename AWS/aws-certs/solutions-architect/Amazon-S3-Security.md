## Ecrypt Bucket using these methods
1. Server-side Encryption (SSE)
   ##  Amazon S3-Encrption (SSE-S3) 
         1. Encryption using keys owned, handlded and managed by AWS
         2. Objects will be encrypted server side 
         3. Encryption typ eis AES-256
         4. Enabled by default for new bukets and objects 
         5. 
    ## Server-Side Encryption with KMS 
        1. Encryption using keys owned, handlded and managed by AWS KMS (Key management service)
        2. KMS Advanatage are ; Can be control by the user , Use cloud trail to audit key uasge 
        3. Must set header ""x-amz-server-side-encryption": "aws.kms"
        4. Objects is encrypted server side
   
        NOTES:
        Using SSE-KMS mahy be impacted by KMS limits
        When ypu uplaod, it calls the "GenerateDatakey" KMS API 
        When you download it calls the derpty KMS API 

    ## Amazon S3 Encryption - SSE-C
        1. Encryption using keys owned, handlded and managed by customers outside the AWS 
        2. Ita a server-side encryption 
        3. Amazon S3 does not store the keuy 
        4. We use HTTPS 
   
 2. Client -side encryption 
        1. We will use the client libraries (Amazon S3 Client-side Encryption Library)
        2. Client will encrypt data before sendind ti to amazon S3 
        3. Client will decrypt data beforen retriving to amazon S3
        4. Customer will fully manage the keys. 

## Encryption in Transit (SSL/TLS)

## S3 Default Encryption
* SSE-S3 encryption is autotmatically applied to new objects stores in s3 bucket
* Default encryption is on by default with SSE-S3 encryption, but it can be changed and a bucket policy can be made to force encryption to the oen you wnats.



## CORS (Cross-Origin Resource Sharing)
* Origin : scheme (Protocol) + host(domain) + port 
* If a client makes cross-origin request on a S3 bucket, we will need to enable the correct CORS headers. 

NOTE: 
CORS is an HTTP-headrer that allows a server to indicate any origin (domain, scheme, and port) other than its own. 

* CORS in S3 is a web browser security that allows you to enable images, assets, files being retrived from one S3 bucket, in case the request is origination from another origin. 
* It allows browser to display content whichb a web server requested from a diffrent origin. 
* 