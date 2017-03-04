---
layout: post
title: "Send html e-mail in PHP using Gmail smtp"
permalink: send-html-mail-in-php-using-gmail-smtp
date: 2017-03-04 22:09:11
comments: true
description: "send html mail in php using gmail smtp"
keywords: "php, email, gmail, html"
categories:"utilities, productive"

tags:

---

Here is a simple one page Contact form example written in PHP

{% highlight php %}
<?php

require_once('class.phpmailer.php');

// Functions to filter user inputs
function filterName($field){
    // Sanitize user name
    $field = filter_var(trim($field), FILTER_SANITIZE_STRING);
    
    // Validate user name
    if(filter_var($field, FILTER_VALIDATE_REGEXP, array("options"=>array("regexp"=>"/^[a-zA-Z\s]+/")))){
        return $field;
    }else{
        return FALSE;
    }
}    
function filterEmail($field){
    // Sanitize e-mail address
    $field = filter_var(trim($field), FILTER_SANITIZE_EMAIL);
    
    // Validate e-mail address
    if(filter_var($field, FILTER_VALIDATE_EMAIL)){
        return $field;
    }else{
        return FALSE;
    }
}
function filterString($field){
    // Sanitize string
    $field = filter_var(trim($field), FILTER_SANITIZE_STRING);
    if(!empty($field)){
        return $field;
    }else{
        return FALSE;
    }
}
 
// Define variables and initialize with empty values
$nameErr = $emailErr = $subjectErr = $commentErr = "";
$name = $email = $subject = $comment = "";
 
// Processing form data when form is submitted
if($_SERVER["REQUEST_METHOD"] == "POST"){
 
    // Validate user name
    if(empty($_POST["name"])){
        $nameErr = 'Please enter your name.';
    }else{
        $name = filterName($_POST["name"]);
        if($name == FALSE){
            $nameErr = 'Please enter a valid name.';
        }
    }
    
    // Validate email address
    if(empty($_POST["email"])){
        $emailErr = 'Please enter your email address.';     
    }else{
        $email = filterEmail($_POST["email"]);
        if($email == FALSE){
            $emailErr = 'Please enter a valid email address.';
        }
    }
    
    // Validate message subject
    if(empty($_POST["subject"])){
        $subjectErr = 'Please let you know about your request briefly.';  
    }else{
        $subject = filterString($_POST["subject"]);
    }
    
    // Validate user comment
    if(empty($_POST["comment"])){
        $commentErr = 'Please enter your comment.';     
    }else{
        $comment = filterString($_POST["comment"]);
        if($comment == FALSE){
            $commentErr = 'Please enter a valid comment.';
        }
    }
    
    // Check input errors before sending email
    if(empty($nameErr) && empty($emailErr) && empty($subjectErr) && empty($commentErr)){
		
	 // Recipient email address
	 $to = 'recipient@domain.tld';
	 
	 // To send HTML mail, the Content-type header must be set
	 $headers  = 'MIME-Version: 1.0' . "\r\n";
	 $headers .= 'Content-type: text/html; charset=iso-8859-1' . "\r\n";
	 
     	 // Create email headers
	 $headers = 'From: '. $email . "\r\n" .
        'Reply-To: '. $email . "\r\n" .
        'X-Mailer: PHP/' . phpversion();
		
	 $mail = new PHPMailer();
        $mail->CharSet =  "utf-8";
	 $mail->IsSMTP();
	 $mail->SMTPAuth = true;
	 $mail->Username = "username@gmail.com";
	 $mail->Password = "**password**";
	 $mail->SMTPSecure = "ssl";  
	 $mail->Host = "smtp.gmail.com";
	 $mail->Port = "465";
 
	 $mail->setFrom($email, $name);
	 $mail->AddAddress($to, 'company contact');
 
	 $mail->Subject  =  $subject;
	 $mail->IsHTML(true);
	 
 	// Compose a simple HTML email message
 	$message = "<html><body>";
 	$message .= "<p style='color:#080;font-size:18px;'>New contact request from the website</p>";
 	$message .= "<table border='1'>";
 	$message .= "<tr><td>Name</td><td>".$name."</td></tr>";
	$message .= "<tr><td>Email</td><td>".$email."</td></tr>";
	$message .= "<tr><td>Subject</td><td>".$subject."</td></tr>";
	$message .= "<tr><td>Message</td><td>".$comment."</td></tr>";
 	$message .= "</table></body></html>";
	
	$mail->Body 	  = $message;
  
	 if($mail->Send())
	      {
	         echo "Message was Successfully Sent)";
	      }
	 else
	      {
	         echo "Mail Error - >".$mail->ErrorInfo;
	      }
				
        
    }
}
?>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Contact Form Example</title>
    <style type="text/css">
        .error{ color: red; }
        .success{ color: green; }
    </style>
</head>
<body>
    <h2>Contact Us</h2>
    <p>Please fill in this form and send us.</p>
    <form action="contact.php" method="post">
        <p>
            <label for="inputName">Name:<sup>*</sup></label>
            <input type="text" name="name" id="inputName" value="<?php echo $name; ?>">
            <span class="error"><?php echo $nameErr; ?></span>
        </p>
        <p>
            <label for="inputEmail">Email:<sup>*</sup></label>
            <input type="text" name="email" id="inputEmail" value="<?php echo $email; ?>">
            <span class="error"><?php echo $emailErr; ?></span>
        </p>
        <p>
            <label for="inputSubject">Subject:</label>
            <input type="text" name="subject" id="inputSubject" value="<?php echo $subject; ?>">
	    <span class="error"><?php echo $subjectErr; ?></span>
        </p>
        <p>
            <label for="inputComment">Comment:<sup>*</sup></label>
            <textarea name="comment" id="inputComment" rows="5" cols="30"><?php echo $comment; ?></textarea>
            <span class="error"><?php echo $commentErr; ?></span>
        </p>
        <input type="submit" value="Send">
        <input type="reset" value="Reset">
    </form>
    <p> <a href="index.php">Simon, Go Back !!</a>	
</body>
</html>
{% endhighlight %} 

The above page requires 'class.phpmailer.php' which can be downloaded [here](https://github.com/PHPMailer/PHPMailer/blob/master/class.phpmailer.php "PHPMailer"). Include it in the same directory as the above file.
