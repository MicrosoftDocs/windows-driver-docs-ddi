---
UID: NS:winbio_ioctl._WINBIO_SUPPORTED_ALGORITHMS
title: _WINBIO_SUPPORTED_ALGORITHMS
author: windows-driver-content
description: The WINBIO_SUPPORTED_ALGORITHMS structure is the OUT payload for IOCTL_BIOMETRIC_GET_SUPPORTED_ALGORITHMS.
old-location: biometric\winbio_supported_algorithms.htm
old-project: biometric
ms.assetid: cb2236f6-409a-4352-a02b-f7763e986d1f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: winbio_ioctl/WINBIO_SUPPORTED_ALGORITHMS, PWINBIO_SUPPORTED_ALGORITHMS structure pointer [Biometric Devices], _WINBIO_SUPPORTED_ALGORITHMS, biometric_ref_44bbda1a-1b9b-42d3-9034-9d0c3c4bac88.xml, WINBIO_SUPPORTED_ALGORITHMS, *PWINBIO_SUPPORTED_ALGORITHMS, WINBIO_SUPPORTED_ALGORITHMS structure [Biometric Devices], PWINBIO_SUPPORTED_ALGORITHMS, biometric.winbio_supported_algorithms, winbio_ioctl/PWINBIO_SUPPORTED_ALGORITHMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winbio_ioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	winbio_ioctl.h
apiname: 
-	WINBIO_SUPPORTED_ALGORITHMS
product: Windows
targetos: Windows
req.typenames: *PWINBIO_SUPPORTED_ALGORITHMS, WINBIO_SUPPORTED_ALGORITHMS
req.product: Windows 10 or later.
---

# _WINBIO_SUPPORTED_ALGORITHMS structure


## -description


The WINBIO_SUPPORTED_ALGORITHMS structure is the OUT payload for <a href="..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_get_supported_algorithms.md">IOCTL_BIOMETRIC_GET_SUPPORTED_ALGORITHMS</a>.


## -syntax


````
typedef struct _WINBIO_SUPPORTED_ALGORITHMS {
  DWORD       PayloadSize;
  HRESULT     WinBioHresult;
  DWORD       NumberOfAlgorithms;
  WINBIO_DATA AlgorithmData;
} WINBIO_SUPPORTED_ALGORITHMS, *PWINBIO_SUPPORTED_ALGORITHMS;
````


## -struct-fields




### -field PayloadSize

Specifies the total size of the payload, which includes the fixed length structure and any variable data at the end.


### -field WinBioHresult

Specifies the HRESULT status of the I/O operation.


### -field NumberOfAlgorithms

Specifies the number of algorithms in the data block.


### -field AlgorithmData

Specifies a structure of type <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_data.md">WINBIO_DATA</a> that contains NULL-terminated UTF-8 OID strings that represent the algorithms supported by the device.


## -see-also

<a href="..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_get_supported_algorithms.md">IOCTL_BIOMETRIC_GET_SUPPORTED_ALGORITHMS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [biometric\biometric]:%20WINBIO_SUPPORTED_ALGORITHMS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

