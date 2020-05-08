# cesarcode
Solve cesar code challenge with PHP

#### Test code in [PHP Tester ONLINE](http://phptester.net/)

````
<?php

$wordsList = [
	"ARGENTINA",
	"BRASIL",
	"BOLIVIA",
	"CHILE",
	"COLÔMBIA",
	"EQUADOR",
	"GEEK HUNTER",
	"PARAGUAI",
	"PERU",
	"REPUBLICA DOMINICANA",
	"URUGUAI"
];


function encryptCesar($input) 
{
	$alphabet = [ 0 => "A", 1 => "B", 2 => "C", 3 => "D", 4 => "E", 5 => "F",
		6 => "G", 7 => "H", 8 => "I", 9 => "J", 10 => "K", 11 => "L", 12 => "M", 
		13 => "N", 14 => "O", 15 => "P", 16 => "Q", 17 => "R", 18 => "S", 
		19 => "T", 20 => "U", 21 => "V", 22 => "X", 23 => "Y", 24 => "Z"
	];
	
	$input = str_split($input);
	
	$return = "";
	
	
	foreach($input as $k => $char) {
		
		foreach($alphabet as $k2 => $letter) {
			
			if($char == $letter && $char != " " && $char != "Z") {
				$newIndex = $k2+3;
				
				$return .= $alphabet[$newIndex];
			} 
			
			if($char == " ") {
				$return .= " ";
			} 
			
			if($char == "Z" && $letter == "Z") {
				$return .= "C";
			}
			
			if($char == "X" && $letter == "X") {
				$return .= "A";
			} 
			
			if($char == "Y" && $letter == "Y") {
				$return .= "B";
			}
		}
	}
	
	return $return . "<br>";
}


function encryptListWords($wordsList)
{
	
	$result = "";
	foreach($wordsList as $input) {
		$result .= "Input: ". $input . " | Output: " . encryptCesar($input);
	}
	
	return $result;
}

echo encryptListWords($wordsList);
````
