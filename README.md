IMAP Action Daemon
==================

Watch an IMAP folder for unread messages that match certain criteria.  If such
messages arrive, run a command.

This is implemented using the IDLE command, so it should give instant
notification.

You will need to create a config file, ~/.imap-actiond.yaml, with the following
layout:

    server: imap.example.com
    ssl: true
    ignore_cert_errors: true
    
    username: maurice
    password: 01189998819991197253
    
    rules:
      - subject: "nagios notifica"
        from: "nagios@example.com"
        command: "aplay -q /usr/share/sounds/ekiga/voicemail.wav"

Valid rule fields are:

* subject
* from
* to
* cc
* body
