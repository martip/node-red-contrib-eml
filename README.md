# node-red-contrib-eml

A [Node-RED](http://nodered.org/) node that parses an EML (email) file.
It basically works as the official [node-red-node-email](https://flows.nodered.org/node/node-red-node-email) input node, accepting a buffer of an EML file as input, instead of fetching it from a mail server.

This node uses the [MailParser](https://nodemailer.com/extras/mailparser/) library, part of the NodeMailer project.

## Install

Either use the `Node-RED Menu - Manage Palette - Install`, or run the following command in your Node-RED user directory - typically `~/.node-red`

    npm install node-red-contrib-eml

## Usage

You pass the content of an EML file, as a buffer, in the `msg.payload`.

After processing, the subject of the email message is loaded into `msg.topic` and `msg.payload` is the plain text body. If there is text/html then that is returned in `msg.html`. `msg.from` and `msg.date` are also set if you need them.

Additionally, `msg.header` contains the complete header object including `to`, `cc` and other potentially useful properties.

Attachments contained in the email message are returned in the `msg.attachments` array.
