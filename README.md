<div align="center">

## PHP\-GTK Window Code


</div>

### Description

Simple explanation of PHP-GTK framework...!
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Bogomil Shopov](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/bogomil-shopov.md)
**Level**          |Intermediate
**User Rating**    |4.6 (23 globes from 5 users)
**Compatibility**  |PHP 4\.0
**Category**       |[Coding Standards](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/coding-standards__8-33.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/bogomil-shopov-php-gtk-window-code__8-462/archive/master.zip)





### Source Code

```
<?PHP
//import the php-gtk library file (dll (win))
dl('php_gtk.dll');
// define variables
  // window
$window =&new GtkWindow();
$window->set_title("Messenger");
  //button
$bt=&new GtkButton("Send value");
$bt2=&new GtkButton("Kill Me!");
   //layout
$adj=&new GtkAdjustment(0,0,400,400,400,400);
$lt=&new GtkLayout($adj,$adj);
  // TextField
global $fld;
$fld= &new GtkEntry();
//functions
function get_value($bt,$window){
     global $fld;
     $str=$fld->get_text();
     echo"Your input:$str";
    }
//element properties
$bt->connect("clicked","get_value", $window);
$bt2->connect_object('clicked', array('gtk', 'main_quit'));
//Layout positon
$lt->put($fld,1,1);
$lt->put($bt,50,50);
$lt->put($bt2,50,100);
//window show
$window->add($lt);
$window->show_all();
Gtk::Main();
?>
```

