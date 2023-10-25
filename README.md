Install:
`composer require cleantalk/remote-calls`

Using:
```php
<?php

$storage_handler = new \Cleantalk\Custom\StorageHandler\StorageHandler();
$api_key = 'your_api_key';

if ( $rc_class::check() ) {
    try {
        $remote_calls = new \Cleantalk\Common\RemoteCalls\RemoteCalls($api_key, $storage_handler);
        die $remote_calls->process();
    } catch ( \\Cleantalk\Common\RemoteCalls\Exceptions\RemoteCallsException $e ) {
        // Do logging here
        die 'FAIL ' . json_encode(array('error' => $exception->getMessage()))
    }
}
```