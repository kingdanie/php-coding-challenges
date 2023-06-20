<!-- Have the function StringChallenge(str,num) take the str parameter and perform a 
Caesar Cipher shift on it using the num parameter as the shifting number. 
A Caesar Cipher works by shifting each letter in the string N places in 
the alphabet (in this case N will be num). Punctuation, spaces, and capitalization 
should remain intact. For example if the string is "Caesar Cipher" and num is 2 
the output should be "Ecguct Ekrjgt".
Once your function is working, take the final output string and concatenate 
it with your ChallengeToken, and then replace every third character with an X. 

Your ChallengeToken: 67kseucpjbd
Examples

Input: "Hello" & num = 4 
Output: Lipps 
Final Output: LiXpsX7kXeuXpjXd

Input: "abc" & num = 0 
Output: abc 
Final Output: abX67XseXcpXbd -->


##The solution

function StringChallenge($str, $num) {
    $arr = [];
    $re = '/[a-z]/i';
    for ($i = 0; $i < strlen($str); $i++) {
        if (preg_match($re, $str[$i])) {
            $arr[] = ord($str[$i]) + $num;
        } else {
            $arr[] = ord($str[$i]);
        }
    }
    for ($i = 0; $i < count($arr); $i++) {
        $arr[$i] = chr($arr[$i]);
    }
    return implode("", $arr);
}

