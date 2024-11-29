# Deno WebRTC Communications 

This library is a support service for a Deno Deploy app:    
https://github.com/nhrones/FreshDiceRTC

I built this because I was having many issues with determinism of the Deploy WebSockets and SSE.   

I decided to simply use Deploy as an app and signal server, and then just rely on WebRTC for real-time game-events. This worked extremely well!   

<br/>

 ![Alt text](./media/Signaling.png)
 
<br/>

This lib includes:    
  *  A Deno-Deploy Signal Service     
        *  Client =  signaling.ts    
        *  Server + Signal-service = FreshDiceRTC -> routes/api/sse.ts    
  *  WebRTC connection module    
  *  A Peer management module

The main issue with this architecture is that all peers are responsible for maintaining a syncronized state. 
 
<br/>

![Alt text](./media/comms.png)
  
