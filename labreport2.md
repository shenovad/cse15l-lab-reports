# Lab Report 2

Shenova Davis  
CSE 15L

## Part 1

```
class Handler implements URLHandler {

    String newChat = "";
    
    public String handleRequest(URI url) {
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("&");

        String chatString = " ";
        String userString = " ";

            for(String param : parameters){
                String[] SingleParameter = param.split("=");
                    if (SingleParameter[0].equals("s")) {
                    chatString = chatString + SingleParameter[1] ;
                    } else if (SingleParameter[0].equals("user")) {
                    userString = userString + SingleParameter[1];
                    }
            }
            String newMessage = userString + ": " + chatString + "\n";
            newChat = newChat + newMessage;
            return newChat;
        }
        return "404 Not Found!";
    }
}
```
