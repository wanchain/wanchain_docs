.. _How to verify install package's SHA256:

********************************************************************************
How to verify install package's SHA256 checksum
********************************************************************************

================================================================================
Windows
================================================================================

The following command will display SHA256 hash value on a Windows operating system ("SHA256" parameter is case sensitive  on certain versions of Windows):

    certutil -hashfile <path>\<filename> SHA256

================================================================================
Linux
================================================================================

The following command will display SHA256 hash value on a Linux operating system:

    sha256sum <path>/<filename>

================================================================================
Mac
================================================================================

The following command will display SHA256 hash value on a Mac operating system.

    openssl dgst -sha256 <path>/<filename>