# Binary verifications

## Terraform signature and PGP verification

Both Terraform SHA256SUM and signature files are verified against [Hashicorp public GPG key](https://www.hashicorp.com/security).

Terraform archives are verified against there SHA256SUMS after donwload.

Theses files need to be added to the [/security](https://github.com/zenika-open-source/terraform-aws-cli/tree/master/security) folder.

They can be downloaded from the [official Terraform releases](https://releases.hashicorp.com/terraform).

## AWS CLI signature and PGP verification

Both AWS CLI archives and signatures files are verified against AWS public GPG key.

The Dockerfile downloads the AWS CLI archive and signature for the build platform (x86_64 or aarch64) and verifies them with the public key stored in [/security/awscliv2.asc](https://github.com/zenika-open-source/terraform-aws-cli/tree/master/security).

If you want to verify artifacts locally, you can download the signature file with this command:

```shell
# Export target aws cli version
export AWS_CLI_VERSION=2.12.5
export AWS_CLI_ARCH=x86_64

# Download signature file
curl -o security/awscli-exe-linux-${AWS_CLI_ARCH}-${AWS_CLI_VERSION}.zip.sig \
  https://awscli.amazonaws.com/awscli-exe-linux-${AWS_CLI_ARCH}-${AWS_CLI_VERSION}.zip.sig
```
