---
UID: NS:ehstorbandmgmt._BAND_SECURITY_INFO
title: _BAND_SECURITY_INFO
author: windows-driver-content
description: The BAND_SECURITY_INFO structure specifies the security information for a band table entry query.
old-location: storage\band_security_info.htm
old-project: storage
ms.assetid: 310F996F-F350-4F25-BC8A-386513908557
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _BAND_SECURITY_INFO, *PBAND_SECURITY_INFO, BAND_SECURITY_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BAND_LOCATION_INFO
req.alt-loc: EhStorBandMgmt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: *PBAND_SECURITY_INFO, BAND_SECURITY_INFO
---

# _BAND_SECURITY_INFO structure



## -description
The <b>BAND_SECURITY_INFO</b> structure specifies the security information for a band table entry query.



## -syntax

````
typedef struct _BAND_LOCATION_INFO {
  ULONG      StructSize;
  LOCKSTATE  ReadLock;
  LOCKSTATE  WriteLock;
  ALGOIDTYPE CryptoAlgoIdType;
  union {
    struct {
      ULONG Offset;
      ULONG Length;
    } CryptoAlgoOidString;
    ULONG  CryptoAlgoNumericId;
  };
  BYTE       Metadata[32];
} BAND_LOCATION_INFO, *PBAND_LOCATION_INFO;
````


## -struct-fields

### -field StructSize

The size of the structure in bytes. Set to <b>sizeof</b>(BAND_SECURITY_INFO).


### -field ReadLock

Whether the band is accessible for reading and how a read lock is affected by a power reset.


### -field WriteLock

Whether the band is accessible for writing and how a write lock is affected by a power reset.


### -field CryptoAlgoIdType

The type of encryption algorithm identifier used. This must be set to <b>AlgoIdTypeOidString</b>.


### -field CryptoAlgoOidString

The encryption algorithm used to protect the data in the band.


### -field Offset

The offset from the beginning of this structure where the encryption algorithm OID string begins.


### -field Length

The length of the OID string identifying the encryption algorithm. This is a byte-length value including a NULL terminator for the OID string.

</dd>
</dl>

### -field CryptoAlgoNumericId

Reserved.


### -field Metadata

A metadata field available for use by a key manager.


## -remarks
Both <b>Readlock</b> and <b>Writelock</b> are <b>LOCKSTATE</b> values and indicate locking state and lock persistence. Their values are one of the following.

<b>CryptoAlgoOidString</b>  specifies the data encryption algorithm only if <b>ENUMBANDS_REPORT_CRYPTO_ALGO</b> is set in the <b>Flags</b> member of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_enumerate_bands_parameters.md">ENUMERATE_BANDS_PARAMETERS</a> in an <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_enumerate_bands.md">IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</a> request. Otherwise, both <b>CryptoAlgoOidString.Offset</b> and <b>CryptoAlgoOidString.Length</b> are set to 0. The following are possible encryption algorithm OID strings returned for <b>CryptoAlgoOidString</b>.

When <b>BAND_SECURITY_INFO</b> is used in an input parameter set, <b>CryptoAlgoIdType</b> and <b>CryptoAlgoOidString</b> are not used and must be set to 0.


## -see-also
<dl>
<dt>
<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_table_entry.md">BAND_TABLE_ENTRY</a>
</dt>
<dt>
<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_enumerate_bands_parameters.md">ENUMERATE_BANDS_PARAMETERS</a>
</dt>
<dt>
<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_create_band.md">IOCTL_EHSTOR_BANDMGMT_CREATE_BAND</a>
</dt>
<dt>
<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_enumerate_bands.md">IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20BAND_SECURITY_INFO structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

