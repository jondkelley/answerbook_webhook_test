# answerbook_webhook_test

## Install
```
pip3 install answerbook_webhook_test

#or

python setup.py install
```

## Environment Variables

You will set up environment variables to modify behavior, here's a table of options below with the defaults

```
LOGDNA_AGENT_KEY=FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
LOGDNA_URL=
OUTPUT_FILE=output.txt
LISTEN_HOST=0.0.0.0
LISTEN_PORT=80
```

*LOGDNA_AGENT_KEY* - optional, will not log to platform if unset

*LOGDNA_URL* - override default platform url

*OUTPUT_FILE* - override default log file to output to

*LISTEN_HOST* - set bind host

*LISTEN_PORT* - set bind port

## Run Server
```
sudo --preserve-env=LOGDNA_AGENT_KEY /usr/local/bin/answerbook_webhook_test
```

or 

```
sudo /usr/local/bin/answerbook_webhook_test
```

## Usage

The server logs any request POST payload sent to /_webhook/resources ... where resources can be any path or name you choose.

For example to post a json blob
```
curl -X POST -d '{"name": "value", "id": "706FBE5FFECEA"}' http://18.218.77.191:80/_webhook/anything_you_make_up_goes_here/path/you/make/up
```

This allows you to configure a webhook system to this and capture data within the logging platform.

