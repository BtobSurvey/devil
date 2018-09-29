# devil
for employees good feeling
<?php
/*
 * BEFORE RUNNING:
 * ---------------
 * 1. If not already done, enable the Google Cloud Resource Manager API
 *    and check the quota for your project at
 *    https://console.developers.google.com/apis/api/cloudresourcemanager
 * 2. This sample uses Application Default Credentials for authentication.
 *    If not already done, install the gcloud CLI from
 *    https://cloud.google.com/sdk and run
 *    `gcloud beta auth application-default login`.
 *    For more information, see
 *    https://developers.google.com/identity/protocols/application-default-credentials
 * 3. Install the PHP client library with Composer. Check installation
 *    instructions at https://github.com/google/google-api-php-client.
 */

// Autoload Composer.
require_once __DIR__ . '/vendor/autoload.php';

$client = new Google_Client();
$client->setApplicationName('Google-CloudResourceManagerSample/0.1');
$client->useApplicationDefaultCredentials();
$client->addScope('https://www.googleapis.com/auth/cloud-platform');

$service = new Google_Service_CloudResourceManager($client);

// TODO: Assign values to desired properties of `requestBody`:
$requestBody = new Google_Service_CloudResourceManager_Project();

$response = $service->projects->create($requestBody);

// TODO: Change code below to process the `response` object:
echo '<pre>', var_export($response, true), '</pre>', "\n";
?>

