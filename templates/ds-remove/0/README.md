# Rancher AWS host cleanup

### Info
This template contains a single alpine based image that runs a check on disk space every minute.

An AWS key and secret are required with permissions to describe instances and terminate instances in order for it to validate the host status or remove it.

If the host is not running on AWS then it will be evacuated but not terminated

Please try this in a test environment first, whilst it has been tested there may well be a use case that has not been tried.

The source code is available at [https://www.github.com/chrisurwin/ds-remove] (https://www.github.com/chrisurwin/ds-remove)

