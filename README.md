- š Hi, Iām @rizsqi
- š Iām interested in ...
- š± Iām currently learning ...
- šļø Iām looking to collaborate on ...
- š« How to reach me ...

<!---
rizsqi/rizsqi is a āØ special āØ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->


<?php

system('clear');
system('python2 banner.py');
echo "Input Ip Address : ";
$add = trim(fgets(STDIN));
class requests{

     public $link;

     public function set_link($link){
        $this->link = $link;
     }


     public function get_link(){
        return $this->link;
     }

}

$req = new requests();

$req->set_link(file_get_contents("http://api.ipstack.com/$add?access_key=70ab8800007bd96cbc5fd3aa509fba22"));

$json = $req->get_link();


$ubah = json_decode($json);
system('clear');
system('python2 banner.py');

echo "\033[92mIp : {$ubah->ip}\n";
echo "Type : {$ubah->type}\n";
echo "Continent code : {$ubah->continent_code}\n";
echo "Continent Name : {$ubah->continent_name}\n";
echo "Country Code : {$ubah->country_code}\n";
echo "Country Name : {$ubah->country_name}\n";
echo "Region Code : {$ubah->region_code}\n";
echo "Region Name : {$ubah->region_name}\n";
echo "City : {$ubah->city}\n";
echo "Zip : {$ubah->zip}\n";
echo "Latitude : {$ubah->latitude}\n";
echo "Longitude : {$ubah->longitude}\n";
echo "Geoname Id : {$ubah->location->geoname_id}\n";
echo "Flag Emoji : {$ubah->location->country_flag_emoji}\n";
echo "Calling Code : {$ubah->location->calling_code}\n";

echo "___________________________________________________________\n";

?>
