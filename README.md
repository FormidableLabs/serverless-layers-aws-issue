# Serverless Packaging, Layers, and AWS Authentication

This repository demonstrates an issue wherein the mere act of packaging (`serverless package`) requires AWS authentication if a layer is included in `serverless.yml`.

See the `serverless` issue at: https://github.com/serverless/serverless/issues/8187

## Usage

Install:

```sh
$ yarn
```

## Issue Reproduction

Run packaging without any AWS credentials (in environment or otherwise):

```sh
$ serverless package
```

**Expected behavior**: Serverless creates a package.

**Actual behavior**: We get an error as follows:

```
  Serverless Error ---------------------------------------

  AWS provider credentials not found. Learn how to set up AWS provider credentials in our docs here: <http://slss.io/aws-creds-setup>.

  Get Support --------------------------------------------
     Docs:          docs.serverless.com
     Bugs:          github.com/serverless/serverless/issues
     Issues:        forum.serverless.com

  Your Environment Information ---------------------------
     Operating System:          darwin
     Node Version:              12.18.3
     Framework Version:         1.81.1 (local)
     Plugin Version:            3.8.3
     SDK Version:               2.3.1
     Components Version:        2.34.9
```

## Notes

If you comment out the layer in configuration then `serverless package` will successfully create a package.


## Maintenance Status

**Archived:** This project is no longer maintained by Formidable. We are no longer responding to issues or pull requests unless they relate to security concerns. We encourage interested developers to fork this project and make it their own!
