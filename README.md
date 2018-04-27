Smart Security Lock App
===  

An application that served as a complement to my second year project, which was a smart security lock using a Raspberry Pi. The whole project was worked on by a team of six, but this app was built by myself and @amirtootooni. While the app communicates with a server for most of its functionality, the server is current down with no plans to put it back up. However, the app's code is here for reference.  

# Main Functions  

## Visit Log  
Upon every instance the `VisitLogFragment` is opened from the Navigation Drawer, the app makes an HTTP request with the server to obtain a JSON string containing the user's visits on their locks. The JSON string is then parsed into `Visit` objects, whose fields refer to the date, time, and whether or not the lock was accessed. These `Visit` objects are then used to format the `VisitCard` objects to display to the user.  

## Locks
Upon every instance the `LocksFragment` is opened from the Navigation Drawer, the app makes an HTTP request with the server to obtain a JSON string containing the user's locks. The JSON string is then parsed into `Lock` objects, which are then used to format the `LockCard` objects. The user can also add new locks to their account by entering the lock's ID.  

# NFC
Upon every log in, the user is given a unique token that is used to trigger the NFC reader to unlock the lock. An ability to share access to an owned lock is provided by giving the ability to change the token that is written by the app to the NFC reader, and the ability for the user to send their own token to other people via text.
