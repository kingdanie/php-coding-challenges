##Back-end Challenge
In the PHP file, write a program to perform a GET request on the route https://coderbyte.com/api/challenges/json/age-counting which contains a data key and the value is a string which contains items in the format: key=STRING, age=INTEGER. Your goal is to count how many items exist that have an age equal to or greater than 50, and print this final value.

Example Input
{"data":"key=IAfpK, age=58, key=WNVdi, age=64, key=jp9zt, age=47"}

Example Output
2
Example Output with ChallengeToken
2:260duqi39lm
Once your function is working, take the final output string and combine it with your ChallengeToken, both in reverse order and separated by a colon.

Your ChallengeToken: ml93iqud062



```php
<?php 

  $ch = curl_init('https://coderbyte.com/api/challenges/json/age-counting');
  curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
  curl_setopt($ch, CURLOPT_HEADER, 0);
  $data = curl_exec($ch);
  curl_close($ch);

  print_r(json_decode($data, true));

?>
```

##The solution
```php
<?php 

  $ch = curl_init('https://coderbyte.com/api/challenges/json/age-counting');
  curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
  curl_setopt($ch, CURLOPT_HEADER, 0);
  $data = curl_exec($ch);
  curl_close($ch);

  //print_r(json_decode($data, true));

  $raw_data = json_decode($data, true)['data'];
  $to_array = explode(', ', $raw_data);
  $interator = 0;
   //print_r($raw_data);
  $reg_pattern = "/age=(\d+)/";
  $age_array = [];

  foreach($to_array as $item) {
    if(strpos($item, 'age=') !== false) {
      
      $aged = pref_match($reg_pattern, $item, $matches);
      $age = $matches[1];
      if ($age >= 50) {
        array_push($age_array, $age);
        $interator++;
      }
    }
  }
$challenge_token = "ml93iqud062";
$result = strrev((string)$interator) . ':' . strrev($challenge_token);
print_r($result);
?>
```
