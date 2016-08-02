If you want to include code samples in the restructured text
source instead of embedding them in the file, copy the 
code samples to this directory.

Add the ``samples/*`` directory to the conf.py 
``excludes_patterns`` configuration to prevent
*duplicate topic* errors in the Sphinx build output.

In each sample file, add the code sample in 
restructured text format. For an example, see the example in the
[auth-req-curl.rst](https://github.com/rackerlabs/docs-common/edit/master/api-guide-template/common-gs/samples/auth-req-curl.rst)
file.
