---
UID: NS:winbio_ioctl._WINBIO_SUPPORTED_ALGORITHMS
title: _WINBIO_SUPPORTED_ALGORITHMS (winbio_ioctl.h)
description: The WINBIO_SUPPORTED_ALGORITHMS structure is the OUT payload for IOCTL_BIOMETRIC_GET_SUPPORTED_ALGORITHMS.
old-location: biometric\winbio_supported_algorithms.htm
tech.root: biometric
ms.assetid: cb2236f6-409a-4352-a02b-f7763e986d1f
ms.date: 02/20/2018
ms.keywords: "*PWINBIO_SUPPORTED_ALGORITHMS, PWINBIO_SUPPORTED_ALGORITHMS, PWINBIO_SUPPORTED_ALGORITHMS structure pointer [Biometric Devices], WINBIO_SUPPORTED_ALGORITHMS, WINBIO_SUPPORTED_ALGORITHMS structure [Biometric Devices], _WINBIO_SUPPORTED_ALGORITHMS, biometric.winbio_supported_algorithms, biometric_ref_44bbda1a-1b9b-42d3-9034-9d0c3c4bac88.xml, winbio_ioctl/PWINBIO_SUPPORTED_ALGORITHMS, winbio_ioctl/WINBIO_SUPPORTED_ALGORITHMS"
ms.topic: struct
f1_keywords:
 - "winbio_ioctl/WINBIO_SUPPORTED_ALGORITHMS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- winbio_ioctl.h
api_name:
- WINBIO_SUPPORTED_ALGORITHMS
product:
- Windows
targetos: Windows
req.typenames: WINBIO_SUPPORTED_ALGORITHMS, *PWINBIO_SUPPORTED_ALGORITHMS
---

# _WINBIO_SUPPORTED_ALGORITHMS structure


## -description


The WINBIO_SUPPORTED_ALGORITHMS structure is the OUT payload for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winbio_ioctl/ni-winbio_ioctl-ioctl_biometric_get_supported_algorithms">IOCTL_BIOMETRIC_GET_SUPPORTED_ALGORITHMS</a>.


## -struct-fields




### -field PayloadSize

Specifies the total size of the payload, which includes the fixed length structure and any variable data at the end.


### -field WinBioHresult

Specifies the HRESULT status of the I/O operation.


### -field NumberOfAlgorithms

Specifies the number of algorithms in the data block.


### -field AlgorithmData

Specifies a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winbio_ioctl/ns-winbio_ioctl-_winbio_data">WINBIO_DATA</a> that contains NULL-terminated UTF-8 OID strings that represent the algorithms supported by the device.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winbio_ioctl/ni-winbio_ioctl-ioctl_biometric_get_supported_algorithms">IOCTL_BIOMETRIC_GET_SUPPORTED_ALGORITHMS</a>
 

 

