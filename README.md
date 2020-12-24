<b>This module is not ready yet!</b>
# SubcommandExecutor
Module for Bukkit plugins. It's a tool to create commands with subcommands easy.

# Features
<ul>
<li>Auto-generation of a help command</li>
<li>Check of a argument count</li>
</ul>

# Maven
After completion, module will be send to main maven repo.
# How to use it
```java
public void onEnable(){
   SubcommandExecutor commandExecutor = new SubcommandExecutor("commandname");

        //When there's no subcommand that can be used to execute
        commandExecutor.setDefaultExecutor((commandSender, command, s, strings) -> { //CommandExecutor as a lambda
            commandSender.sendMessage("Command list - /commandname help.");
            return false;
        });
        
        executor.addCommandExecutor(
                "subcommandName",
                "description of a subcommand used for help subcommand",
                new int[]{1}, // Command gets one parameter, none parameters or more than 1 it will be an error
                (commandSender, command, s, strings) -> { //CommandExecutor as a lambda, again
                    testString[0] = "create";
                    return false;
                });
       
       executor.addCommandExecutor(
                "nextSubcommandName",
                "description of a next subcommand",
                new int[]{0,1}, // Command gets zero or one parameter, if player enters more than 1 it will be an error
                (commandSender, command, s, strings) -> { //CommandExecutor as a lambda
                    testString[0] = "create";
                    return false;
                });
                
       getCommand("commandname").setExecutor(commandExecutor);
}
```
