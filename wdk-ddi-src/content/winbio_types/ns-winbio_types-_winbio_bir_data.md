---
UID: NS:winbio_types._WINBIO_BIR_DATA
title: "_WINBIO_BIR_DATA"
author: windows-driver-content
description: The WINBIO_BIR_DATA structure contains the location and size of a block in a BIR. The offset is measured from the beginning of the WINBIO_BIR structure.
old-location: biometric\winbio_bir_data.htm
old-project: biometric
ms.assetid: c9ce383e-277d-4fed-839b-8539554f654c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PWINBIO_BIR_DATA structure pointer [Biometric Devices], biometric.winbio_bir_data, _WINBIO_BIR_DATA, WINBIO_BIR_DATA structure [Biometric Devices], biometric_ref_8f527949-820e-416e-952d-8dd3bdf543f6.xml, PWINBIO_BIR_DATA, *PWINBIO_BIR_DATA, winbio_types/PWINBIO_BIR_DATA, winbio_types/WINBIO_BIR_DATA, WINBIO_BIR_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winbio_types.h
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
-	winbio_types.h
apiname:
-	WINBIO_BIR_DATA
product: Windows
targetos: Windows
req.typenames: WINBIO_BIR_DATA
req.product: Windows 10 or later.
---

# _WINBIO_BIR_DATA structure


## -description


The WINBIO_BIR_DATA structure contains the location and size of a block in a BIR. The offset is measured from the beginning of the <a href="..\winbio_types\ns-winbio_types-_winbio_bir.md">WINBIO_BIR</a> structure.


## -syntax


````
typedef struct _WINBIO_BIR_DATA {
  ULONG Size;
  ULONG Offset;
} WINBIO_BIR_DATA, *PWINBIO_BIR_DATA;
````


## -struct-fields




### -field Size

Specifies the size, in bytes, of a block in the BIR.


### -field Offset

Specifies the offset, in bytes, of the block within the BIR.


## -see-also

<a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_capture_data.md">WINBIO_CAPTURE_DATA</a>

<a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_data.md">WINBIO_DATA</a>

<a href="..\winbio_types\ns-winbio_types-_winbio_bir_header.md">WINBIO_BIR_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [biometric\biometric]:%20WINBIO_BIR_DATA structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

