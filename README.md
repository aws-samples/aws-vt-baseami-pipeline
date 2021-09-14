## AWS Xilinx VT Base AMI Build Pipeline
To facilitate getting started with the Xilinx U30 video transcoding instances. We have included some sample build scripts based on Packer to build base AL2, Ubuntu18.04, as well as ECS and EKS base AMIs. Included are sample buildspecs which you integrate with a CodeBuild/CodePipeline for automatic builds.

## Packer Instructions
In the `xilinx-u30-ami_base` dir you will find packer scripts for Amazon Linux 2 and Ubuntu 18.04. Generally you just need to modify the `variables:{}` json and execute the packer build
````json
"variables": {
    "region": "us-east-1",
    "flag": "al2-base",
    "subnet_id": "subnet-baff22e5",
    "security_groupids": "sg-053996a563511a3c6,sg-050407dfb1c555723",
    "build_ami": "ami-02354e95b39ca8dec",
    "xilinx-video-sdk_version": "v1.0",
    "xilinx-video-releasedir": "U30_Amazon_2.0_v1.5_20210827"
  },
````  
After filling in the `variables` check that the packer script is validated.
````
packer validate xilinx-vt-al2.yml
packer build xilinx-vt-al2.yml
````
## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

This package depends on and may incorporate or retrieve a number of third-party
software packages (such as open source packages) at install-time or build-time
or run-time ("External Dependencies"). The External Dependencies are subject to
license terms that you must accept in order to use this package. If you do not
accept all of the applicable license terms, you should not use this package. We
recommend that you consult your company’s open source approval policy before
proceeding.

Provided below is a list of External Dependencies and the applicable license
identification as indicated by the documentation associated with the External
Dependencies as of Amazon's most recent review.

THIS INFORMATION IS PROVIDED FOR CONVENIENCE ONLY. AMAZON DOES NOT PROMISE THAT
THE LIST OR THE APPLICABLE TERMS AND CONDITIONS ARE COMPLETE, ACCURATE, OR
UP-TO-DATE, AND AMAZON WILL HAVE NO LIABILITY FOR ANY INACCURACIES. YOU SHOULD
CONSULT THE DOWNLOAD SITES FOR THE EXTERNAL DEPENDENCIES FOR THE MOST COMPLETE
AND UP-TO-DATE LICENSING INFORMATION.

YOUR USE OF THE EXTERNAL DEPENDENCIES IS AT YOUR SOLE RISK. IN NO EVENT WILL
AMAZON BE LIABLE FOR ANY DAMAGES, INCLUDING WITHOUT LIMITATION ANY DIRECT,
INDIRECT, CONSEQUENTIAL, SPECIAL, INCIDENTAL, OR PUNITIVE DAMAGES (INCLUDING
FOR ANY LOSS OF GOODWILL, BUSINESS INTERRUPTION, LOST PROFITS OR DATA, OR
COMPUTER FAILURE OR MALFUNCTION) ARISING FROM OR RELATING TO THE EXTERNAL
DEPENDENCIES, HOWEVER CAUSED AND REGARDLESS OF THE THEORY OF LIABILITY, EVEN
IF AMAZON HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGES. THESE LIMITATIONS
AND DISCLAIMERS APPLY EXCEPT TO THE EXTENT PROHIBITED BY APPLICABLE LAW.

Xilinx Video SDK (https://github.com/Xilinx/video-sdk) - LGPL-3.0, custom Xilinx license
