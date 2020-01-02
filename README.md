# react-native-camera-t

# build error fix
make sure you're either running a metro server (run 'react-native start')

https://dev.to/hmadhsan/unable-to-load-script-react-native-4gba


You have to follow these simple four steps whenever you face this issue

1) Open your Project folder go to an android folder then app folder then src folder then main folder and just make a blank folder named "assets".(project\android\app\src\main\assets).

2) Back to the project folder, open node_modules, find metro-config and open it, go to src folder then go to defaults folder and then open the blacklist.js file and replace

var sharedBlacklist = [
/node_modules[/\]react[/\]dist[/\]./,
/website\/node_modules\/./,
/heapCapture\/bundle.js/,
/.\/tests\/./
];

with

var sharedBlacklist = [
/node_modules[\/\]react[\/\]dist[\/\]./,
/website\/node_modules\/./,
/heapCapture\/bundle.js/,
/.\/tests\/./
];

this code.

3) Back to the project folder and open command prompt (cmd), paste this code

react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res

and hit enter to install it.

4) now run your command react-native run-android or ios (if you do development on ios).
