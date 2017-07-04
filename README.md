# Netcat Mail

Minimalistic SMPT email command to send email using netcat

## Key Advantages
##### Increased security
`netcat-mail` reduces exposure to security attacks-- it does not run an email server to receive email eliminating open ports, and it's only active during the time it's sending emails out.

##### Minimal system load
`netcat-mail` is only run while sending emails out, and the email script is minimalistic-- this eliminates the need for a continuously running email daemon, and reduces system load and memory usage compared to a system using a full featured email server.

## Purpose
`netcat-mail` is intended to be used primarily to **forward log files to a mail server**, in environments that not require full `mail` support. This is often the case in desktop systems, where users do not need a full email server.

In server environments, log files can be forwarded to a logging master server, and `netcat-mail` is not as useful, except for smaller setups without a logging server.

## Quick Start

### Usage

The common usage for a short email is:
~~~bash
$  netcat-mail [-s SUBJECT_LINE] RECIPIENT_ADDRESS <<< "EMAIL_BODY"
~~~

For a longer email with multiple lines:
~~~bash
$  netcat-mail [-s SUBJECT_LINE] RECIPIENT_ADDRESS <<- END
	FIRST LINE OF EMAIL BODY
	LINE TWO
	...
	LAST LINE
END
~~~

To email a body outlined in a file:
~~~bash
$  netcat-mail [-s SUBJECT_LINE] RECIPIENT_ADDRESS < FILE_WITH_EMAIL_BODY
~~~

### Installation
* Download netcat-mail.
* Make it executable:
~~~bash
$  chmod u+x netcat-mail
~~~

To use `netcat-mail` as a replacement for `mail`, move `netcat-mail` to `/bin` and rename it as `mail`:
~~~bash
$  sudo mv netcat-mail /bin/mail
~~~

## Dependencies
`netcat-mail` requires netcat (`nc`).

## License
MIT license. See the LICENSE file for details. 

