# Users

User objects, followings and followed videos.

## Functions

```$token``` is an optional parameter, but required to be set somewhere.

```php
<?php

// User object
user($user);

// Authenticated user object
authenticatedUser($token);

// An authenticated user is following these channels
streamsFollowed($token);

// An authenticated user is following these videos
videosFollowed($token);

```

## Example Usage

File: ```app/Https/Controllers/UsersController.php```

```php
<?php

namespace App\Http\Controllers;

use TwitchApi;
use App\Http\Requests;
use Illuminate\Http\Request;
use App\Http\Controllers\Controller;

class UsersController extends Controller
{
    public function user()
    {
        return TwitchApi::user('zarlach');
    }

    public function authenticatedUser()
    {
        TwitchApi::setToken('xxxxxxxxxxxxxx');

        return TwitchApi::authenticatedUser();
    }
}
```