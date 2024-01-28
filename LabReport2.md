Part 1 :
`import java.io.IOException;
import java.net.URI;
import java.util.ArrayList; 

class Handler implements URLHandler {
  ArrayList<String> lines = new ArrayList<String>();

  public String handleRequest(URI url){
    String query = url.getQuery();
    if(url.getPath().equals("/add-message")) {
      if(query.startsWith("s=")) { //s=add-message?s=message&user=name
        String[] v1 = query.split("="); //{s,message&user,name}
        String[] v2=v1[1].split("&"); //{message,user}
        lines.add(v1[2]+": ");
        lines.add(v2[0]);
        lines.add("\n");
        return String.join("",lines);
      }
      else {
        return "/add-message requires a query parameter s\n";
      }
    }
    else {
      return String.join("\n", lines) + "\n"; //prints what is in lines
    }
  }
}`

class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}

Examples 1: 

For this example, the main method was called and the value of `args[0]` was 3822 which was saved as the port number. Then the Server method was called with this port number and the handler I wrote in ChatServer.java. In the handler class I have ArrayList of Strings called lines which gets intialised to being empty each time the server method runs. After this: 
- The `handleRequest` function is then ran with `https://0-0-0-0-4567-38r14p1dr548jv8jatuoka0pck.us.edusercontent.com/add-message?s=Hello&user=Kiara` as the value of `URL url`.
- The `String query` variable is set to  `/add-message?s=Hello&user=Kiara`.
- Since the path starts with  `/add-message` and the query starts with `s=` the value of v1 is the query split at `=` resulting to `{"s","hello&user","Kiara"}`.
- The value of `v2` is `v1[1]` split at the `&` which results to `{"hello","user"}.
- `Kiara` is added to lines and then `Hello` is added to `lines` as they are `v1[2]` and `v2[0]` respectively.
- The for loop is exectued from `i=0` to i`<lines.size` which is currently 2. 
- The value of `String user` is `Kiara` (at index 0 of `lines`) and the value of `String message` is `Hello` (at index 1 of `lines`)
- After this the for loop ends as `i` get incremented by 2 and is no longer less than 2. 
- Then the value of user with a colon and the message are printed out on the screen resulting to the output in the photo above.

Example 2: 

Part 2: 

Absolute path to the private key for my SSH key for logging into ieng6: 

![Image](ssh1.png) 

Absolute path to the public key for my SSH key for logging into ieng6:


Terminal interaction where I log into my ieng6 account without being asked for a password: 

Part 3: 
talk about learning about creating a server and remotley connecting to ieng6



