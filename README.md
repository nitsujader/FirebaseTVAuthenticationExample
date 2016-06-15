# FirebaseTVAuthenticationExample
Example project to demonstrate Firebase login on Android TV. 

Compiled against Android Studio 2.1.2
SDK Tools v25.1.7
SDK Platform-Tools v23.1
Build-Tools 23.0.3
Google Play Services Rev 30 (Google services 3.0.0)

Be sure to replace server url and login credentials in LoginActivity.java

To login, run app then press the "SIGN IN OR REGISTER" button. The expected behavior is a progress indicator appearing, followed by the login form returning, then a Toast indicating the status of the login event (completion and success or failure).

On a physical device the expected behavior should be what happens. On an emulator (with or without Google APIs), the progress window will never go away because onComplete or onAuthStateChanged will never get called.

Tested functional on a Nexus 5 (6.0.1)
Tested non-functional Nexus 5 Emulator (6.0.0 with and without Google APIs), Android TV (1080p) emulator (API 21 & 23 tested)

Stack trace from a successful login:
06-14 23:49:36.814 8178-8178/com.justinreda.firebasetvauthenticationexample D/AuthStateChanged: No user is signed in.
06-14 23:49:37.500 8178-8191/com.justinreda.firebasetvauthenticationexample D/FirebaseAuth: Notifying listeners about a sign-out event.
06-14 23:49:37.512 8178-8178/com.justinreda.firebasetvauthenticationexample D/FirebaseApp: Notifying auth state listeners.
06-14 23:49:37.512 8178-8178/com.justinreda.firebasetvauthenticationexample D/FirebaseApp: Notified 1 auth state listeners.
06-14 23:49:37.512 8178-8178/com.justinreda.firebasetvauthenticationexample D/AuthStateChanged: User is signed in with uid: 6b0249fa-ffa4-4a31-b41d-23c727e61737
06-14 23:49:37.531 8178-8191/com.justinreda.firebasetvauthenticationexample D/FirebaseAuth: Notifying listeners about user ( 6b0249fa-ffa4-4a31-b41d-23c727e61737 ).
06-14 23:49:37.545 8178-8178/com.justinreda.firebasetvauthenticationexample D/FirebaseApp: Notifying auth state listeners.
06-14 23:49:37.546 8178-8178/com.justinreda.firebasetvauthenticationexample D/FirebaseApp: Notified 1 auth state listeners.
06-14 23:49:37.546 8178-8178/com.justinreda.firebasetvauthenticationexample D/AuthStateChanged: User is signed in with uid: 6b0249fa-ffa4-4a31-b41d-23c727e61737
06-14 23:49:37.546 8178-8178/com.justinreda.firebasetvauthenticationexample D/LoginActivity 130: onComplete: 
06-14 23:49:37.559 8178-8178/com.justinreda.firebasetvauthenticationexample D/LoginActivity 136: onSuccess user is null? false
06-14 23:49:37.627 8178-8229/com.justinreda.firebasetvauthenticationexample V/RenderScript: 0x994a9000 Launching thread(s), CPUs 4
06-14 23:49:42.113 8178-8223/com.justinreda.firebasetvauthenticationexample I/FA: Tag Manager is not found and thus will not be used
                                                                                  
                                                                                  --------- beginning of system
06-14 23:49:46.869 8178-8213/com.justinreda.firebasetvauthenticationexample E/DynamiteModule: Failed to load module descriptor class: Didn't find class "com.google.android.gms.dynamite.descriptors.com.google.firebase.auth.ModuleDescriptor" on path: DexPathList[[zip file "/data/app/com.justinreda.firebasetvauthenticationexample-2/base.apk"],nativeLibraryDirectories=[/data/app/com.justinreda.firebasetvauthenticationexample-2/lib/arm, /vendor/lib, /system/lib]]


Stack trace from a hanging login (the problem):
06-14 23:47:06.360 2362-2362/com.justinreda.firebasetvauthenticationexample D/AuthStateChanged: No user is signed in.
06-14 23:47:06.360 2362-2375/com.justinreda.firebasetvauthenticationexample E/DynamiteModule: Failed to load module descriptor class: Didn't find class "com.google.android.gms.dynamite.descriptors.com.google.firebase.auth.ModuleDescriptor" on path: DexPathList[[zip file "/data/app/com.justinreda.firebasetvauthenticationexample-1/base.apk"],nativeLibraryDirectories=[/data/app/com.justinreda.firebasetvauthenticationexample-1/lib/x86, /vendor/lib, /system/lib]]
06-14 23:47:06.364 2362-2375/com.justinreda.firebasetvauthenticationexample W/GooglePlayServicesUtil: Google Play Store is neither installed nor updating.
