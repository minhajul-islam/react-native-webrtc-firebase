# react native web-rtc firebase
# Workable calling app in local network need to set global(turn/sturn server)[MINHAJ]

Minimal react native web-etc example with Firebase

## web-rtc

1.STUN is used to answer the question “what is my public IP address?”” and then share the answer with the other user in the session, so he can try and use that address to send media directly.

2.TRUN is used to relay the media through it (so it costs more in bandwidth costs), and is used when you can’t really reach the other user directly.

A few quick thoughts here:

You need both STUN and TURN to make WebRTC work. You can skip STUN if the other end is a media server. You will need TURN even if your other end of the session is a media server on a public IP address Don’t use free STUN servers in your production environment. And don’t never ever use “free” TURN servers If you deploy your own servers, you will need to place the TURN servers as close as possible to your users, which means handling TURN geolocation TURN servers don’t have access to the media. Ever. They don’t pose a privacy issue if they are configured properly, and they can’t be used by you or anyone else to record the conversations Prefer using paid managed TURN servers instead of hosting your own if you can Make sure you configure NAT traversal sensibly. Here’s a free 3-part video course on effectively connecting WebRTC sessions
