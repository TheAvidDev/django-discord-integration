# Django Discord Integration

Discord integration for Django, supporting error reporting via webhooks.

## Installation
```bash
$ pip install django-discord-integration
```

In your `settings.py`, add the following:
```python
INSTALLED_APPS = (
    'discord_integration',
    'solo',
    ...
)
```

Next, migrate the database:
```
$ python manage.py migrate
```

Finally, set the Discord webhook URL in the Django admin, as well as the bot username and avatar URL if necessary.


## Sample Logging Configuration

```python
LOGGING = {
    'handlers': {
        'discord_integration': {
            'level': 'ERROR',
            'class': 'discord_integration.log.DiscordMessageHandler',
        },
    },
    'loggers': {
        'handlers': ['discord_integration'],
    },
}
```
## Changes
* Limited webhook message to the first 5 lines because any more is unnecessary, only containing constant information not directly related to the specific message.

## Copyright Notice
Django Discord Integration - Discord integration for Django, supporting error reporting via webhooks.
Copyright (C) 2019 Ninjaclasher

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published
by the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see https://github.com/Ninjaclasher/django-discord-integration/blob/master/LICENSE.
 
