# OpenAPI Spec validator

[![Package Version](https://img.shields.io/pypi/v/openapi-spec-validator.svg)](https://pypi.python.org/pypi/openapi-spec-validator)
[![Build Status](https://travis-ci.org/dtkav/openapi-spec-validator.svg?branch=master)](https://travis-ci.org/dtkav/openapi-spec-validator)
[![Code Coverage](https://img.shields.io/codecov/c/github/dtkav/openapi-spec-validator/master.svg?style=flat)](https://codecov.io/github/dtkav/openapi-spec-validator?branch=master)
[![PyPI Version](https://img.shields.io/pypi/pyversions/openapi-spec-validator.svg)](https://pypi.python.org/pypi/openapi-spec-validator)
[![PyPI Format](https://img.shields.io/pypi/format/openapi-spec-validator.svg)](https://pypi.python.org/pypi/openapi-spec-validator)
[![PyPI Status](https://img.shields.io/pypi/status/openapi-spec-validator.svg)](https://pypi.python.org/pypi/openapi-spec-validator)


## Fork Notes

This repo was forked from https://github.com/p1c2u/openapi-spec-validator
It has a few minor changes:
1. adds support for python2.7
2. drops support for python3.3 (it has been end-of-life'd)
3. removes extraneous network call when validating swagger2 specs

I'm working on getting all of these changes upstreamed.


## About

OpenAPI Spec Validator is a Python library that validates OpenAPI Specs against the [OpenAPI 2.0 (aka Swagger)](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/2.0.md) and [OpenAPI 3.0.0](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.0.md) specification. The validator aims to check for full compliance with the Specification.

## Installation

    $ pip install openapi-spec-validator

## Usage

### Command Line Interface

Straight forward way:

```bash
$ openapi-spec-validator some.yaml
```

or more pythonic way:

```bash
$ python -m openapi_spec_validator some.yaml
```

### Examples

Validate spec:

```python

from openapi_spec_validator import validate_spec

validate_spec(spec_dict)
```

Add `spec_url` to validate spec with relative files:

```python

from openapi_spec_validator import validate_spec

validate_spec(spec_dict, spec_url='file:///path/to/spec/openapi.yaml')
```

You can also validate spec from url:

```python

from openapi_spec_validator import validate_spec_url

validate_spec_url('http://example.com/openapi.json')
```

If you want to iterate through validation errors:

```python

from openapi_spec_validator import openapi_v3_spec_validator

errors_iterator = openapi_v3_spec_validator.iter_errors(spec)
```

## Related projects

* [openapi-core](https://github.com/p1c2u/openapi-core) is a Python library that adds client-side and server-side support for the OpenAPI.

## License

Copyright (c) 2017, Artur Maciag, All rights reserved.
Apache v2
