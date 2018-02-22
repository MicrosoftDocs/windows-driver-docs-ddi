---
UID: NS:ndis.BINARY_DATA
title: BINARY_DATA
author: windows-driver-content
description: The BINARY_DATA structure contains the binary data of a named entry in the registry.
old-location: netvista\binary_data.htm
old-project: netvista
ms.assetid: 2d629905-49aa-4b66-83f3-0aecb72b73ea
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: BINARY_DATA, BINARY_DATA structure [Network Drivers Starting with Windows Vista], ndis/BINARY_DATA, netvista.binary_data, ndis_configuration_ref_50fc50e5-52d2-4e25-a03b-6c581e50fef1.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers in Windows Vista. Supported for NDIS   5.1 drivers in Windows XP.
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
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	BINARY_DATA
product: Windows
targetos: Windows
req.typenames: BINARY_DATA
---

# BINARY_DATA structure


## -description


The BINARY_DATA structure contains the binary data of a named entry in the registry.


## -syntax


````
typedef struct {
  USHORT Length;
  PVOID  Buffer;
} BINARY_DATA;
````


## -struct-fields




### -field Length

The length, in bytes, of the data that the 
     <b>Buffer</b> member points to.


### -field Buffer

Pointer to a buffer containing the binary data.


## -remarks



The BINARY_DATA structure is used in the 
    <b>ParameterData</b> member of the 
    <a href="..\ndis\ns-ndis-_ndis_configuration_parameter.md">
    NDIS_CONFIGURATION_PARAMETER</a> structure.




## -see-also

<a href="..\ndis\ns-ndis-_ndis_configuration_parameter.md">NDIS_CONFIGURATION_PARAMETER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20BINARY_DATA structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

