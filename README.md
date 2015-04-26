Filtrate - App Rating Reminder (and Filter)
============

A simple rating reminder that filters incoming input.

![Screenshot 1][1]![Screenshot 2][2]

## Download

A JCenter repo will be provided once the API has reached a more stable state. In the mean time, you
would need to download the source and merge it to your project yourself in order to use it.

## Usage

Filtrate can be used with just a few method calls like below:

```
class SampleActivity extends FragmentActivity implements OnRateListener {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        ...
        Filtrate.with(this, this).checkAndShowIfQualify();
        ...
    }

    @Override
    public void onRatedAboveThreshold() {
        // Do what you need to do here..
    }

    @Override
    public void onRatedBelowThreshold() {
        // ..and also here.
    }

}
```

However, you could also alter its default behaviour to fit your use case via a set of APIs that will be
described below.

## API

Filtrate comes predefined with a default behaviour so that it can be used almost instantly. However
you can use these API to alter them to your liking:

```
...
Filtrate.with(Activity, OnRateListener)
        .setRateCancelListener(OnRateCancelListener) // Set an optional listener to handle prompt dismissal.
        .setInitialLaunchThreshold(int) // Set how many launch before the first prompt should show up.
        .setRetryPolicy(RetryPolicy) // Set how Filtrate should retry when user dismissed the prompt.
        .setAcceptableRateThreshold(int) // Set how many stars should be considered "acceptable".
        .setRatePromptText(String) // Set an optional prompt text to replace the default.
        .setSkipButtonText(String) // Set an optional skip button text to replace the default.
        .checkAndShowIfQualify();
...
```

## Credit

This library was hugely inspired by [PomepuyN](https://github.com/PomepuyN)'s awesome [Discreet App Rate](https://github.com/PomepuyN/discreet-app-rate) library.

## License

```
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
```

[1]: http://i.imgur.com/j4y7rMs.png?2
[2]: http://i.imgur.com/XEOatsU.png?2