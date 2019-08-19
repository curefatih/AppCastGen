# AppCast

  App Cast is a broadcast service that helps to real time broadcast a streamers application.
  The difference from the other platforms that viewers can effect the streamers application if they are permitted.

## Design 

  ![Design Diagram](/img/DesignDiagram.png)

  - ### Desktop App

    It consist of 2 part (it can be 3 if we count the ffmpeg part in Desktop App). Main task of Desktop App is the serve and effect the 'stream app'.
      
      - #### part: Event Listener

          Event Listener part takes care of the viewers/participants actions. If there is a action Event Listener will transmit the action to the 'stream app' these actions
      
      - #### part: Stream App

          Stream App side takes the Event Listener data and apply these actions to the 'stream app'
    
    > Java | Python | NodeJS- Electron?(probably not) | Rust Gui(Azul)?

  - ### FFMPEG

    The FFMPEG part of project takes care of the stream the stream app window captures and transmit the stream to the Media Server

  - ### Media Server

    Takes the stream and transmit to the viewers/participants.

    > GoLang | PHP | Rust? | Python 
    
    > need speed on this side

  - ### Web Client

    Serve the video stream. There is posible two behaviour.

    | Client State | Behaviour |
    | ----------- | ----------- |
    | Viewer | Show the stream as a video |
    | Participant | Show stream as canvas and send own actions to the 'Request Server' |

    > Vue.Js* | Canvas | Buefy*

    > *Conclusive

  - ### Request Server

    Takes the actions from Web Client and emits the aciton to the Desktop App's Listener (Event Listener)

  - ### Web Server & Database

    Organize the web stuffs

