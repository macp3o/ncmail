# NC Mail

Minimalistic mail command to post email out.

## Key Advantages
##### Increased security
`ncmail` reduces exposure to security attacks-- it does not run an email server to receive email eliminating open ports, and it's only active during the time it's sending emails out.

##### Minimal system load
`ncmail` is only run while sending emails out, and the email script is minimalistic-- this eliminates the need for a continuously running email daemon, and reduces system load and memory usage compared to a system using a full featured email server.

## Purpose
`ncmail` is intended to be used primarily to **forward log files to a mail server**, in environments that not require full `mail` support. This is often the case in desktop systems, where users do not need a full email server.

In server environments, log files can be forwarded to a logging master server, and `ncmail` is not as useful, except for smaller setups without a logging server.

## Quick Start

### Usage

The common usage for a short email is:
~~~bash
	$  ncmail [-s SUBJECT_LINE] RECIPIENT_ADDRESS <<< "EMAIL_BODY"
~~~

For a longer email with multiple lines:
~~~bash
	$  ncmail [-s SUBJECT_LINE] RECIPIENT_ADDRESS <<- END
			FIRST LINE OF EMAIL BODY
			LINE TWO
			...
			LAST LINE
		END
~~~

To email a body outlined in a file:
~~~bash
	$  ncmail [-s SUBJECT_LINE] RECIPIENT_ADDRESS < FILE_WITH_EMAIL_BODY
~~~

### Installation
* Download ncmail.
* Make it executable:
~~~bash
	$  chmod u+x ncmail
~~~

To use `ncmail` as a replacement for `mail`, additionally move `ncmail` to `/bin` and rename it as `mail`:
~~~bash
	$  sudo mv ncmail /bin/mail
~~~

## Dependencies
`ncmail` requires netcat (`nc`).

## License
MIT license. See the LICENSE file for details. 

