<div align="center">

## counter


</div>

### Description

Shows how to create a counter, as well as record the date and time into a file.
 
### More Info
 
Two files are read to keep track of the hits, one called "count.txt" and another called "ip.txt". You may change these if you wish.

You must make sure that you create a blank textfile called count.txt before you run this script, otherwise it will give you errors the first time it runs, after the first run, it will be fine.

It displays the amount of hits as well as the ip address of the user.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Gowin Down](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/gowin-down.md)
**Level**          |Beginner
**User Rating**    |4.3 (13 globes from 3 users)
**Compatibility**  |PHP 3\.0, PHP 4\.0
**Category**       |[Internet/ Browsers/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-browsers-html__8-9.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/gowin-down-counter__8-301/archive/master.zip)

### API Declarations

```
// I don't care what you do with this
// code, use it for whatever you want.
```


### Source Code

```
<?PHP
 // Place the location of files into variables
 $location_counter = "count.txt";
 $location_ip = "ip.txt";
 // Finds how many people have visited and adds one to it
 $counter = join('', file($location_counter));
 trim($counter);
 $counter++;
 // Print lines to the screen
 echo "<html><body><center><h1>COUNTER</h1>";
 echo "<p>You are visitor number: $counter</p>";
 echo "<p>Your IP address is: $REMOTE_ADDR</p>";
 echo "</center></body></html>";
 // Changes the value of the counter in the count.txt file
 $fp = fopen($location_counter,"w");
 fputs($fp, $counter);
 fclose($fp);
 // Adds one more ip address to the end of the ip.txt file
 $date = date("H:i:s d M, Y");
 $fp = fopen($location_ip,"a");
 fputs($fp, "Date: $date IP: $REMOTE_ADDR \n");
 fclose($fp);
?>
```

