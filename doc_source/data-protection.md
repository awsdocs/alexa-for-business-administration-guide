# Data protection in Alexa for Business<a name="data-protection"></a>

The Alexa for Business console collects data necessary to set up, configure, and manage Alexa devices being operated by Alexa for Business\. Specifically, Alexa for Business collects emails that are used to invite employees or others to link their personal accounts to their corporate Alexa for Business account\. In addition, the Alexa system collects and stores voice data used to interact with Alexa, as well as responses, in order to improve Alexa features, such as speech recognition and natural language understanding\.

To secure your content, Alexa for Business and Alexa provides multiple methods to clear voice and transcript data from the Alexa system, including the Alexa for Business console, APIs, and voice commands\. You can also choose not to have your data annotated by humans, so it will only be used for machine learning\.

## Data encryption<a name="data-encryption"></a>

All customer\-specific data used in Alexa for Business and Alexa is encrypted at rest and in transit using customer master keys \(CMK\) provided by AWS Key Management Service \(AWS KMS\)\.

### Encryption at rest<a name="encryption-rest"></a>

Customer\-specific data used in Alexa for Business is encrypted using an AWS managed CMK\.

### Encryption in transit<a name="encryption-transit"></a>

Alexa for Business uses secure connections between Alexa/Echo devices and the Alexa cloud that are encrypted using TLS 1\.2\. Alexa data is encrypted using a CMK owned by the Alexa team\.

### Key management<a name="key-management"></a>

Customers cannot manage the encryption keys used with Alexa for Business\.