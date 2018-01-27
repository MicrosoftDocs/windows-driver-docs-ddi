---
UID: NS:ndisndk._NDIS_OPEN_NDK_ADAPTER_PARAMETERS
title: _NDIS_OPEN_NDK_ADAPTER_PARAMETERS
author: windows-driver-content
description: The NDIS_OPEN_NDK_ADAPTER_PARAMETERS structure specifies parameters to open an NDK adapter instance on the NDK-capable miniport adapter.
old-location: netvista\ndis_open_ndk_adapter_parameters.htm
old-project: netvista
ms.assetid: AC8D4FA1-59E0-4934-A6C5-EA2E645C53FA
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: *PNDIS_OPEN_NDK_ADAPTER_PARAMETERS, NDIS_OPEN_NDK_ADAPTER_PARAMETERS, ndisndk/NDIS_OPEN_NDK_ADAPTER_PARAMETERS, netvista.ndis_open_ndk_adapter_parameters, _NDIS_OPEN_NDK_ADAPTER_PARAMETERS, PNDIS_OPEN_NDK_ADAPTER_PARAMETERS, ndisndk/PNDIS_OPEN_NDK_ADAPTER_PARAMETERS, PNDIS_OPEN_NDK_ADAPTER_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], NDIS_OPEN_NDK_ADAPTER_PARAMETERS structure [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndisndk.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ndisndk.h
apiname: 
-	NDIS_OPEN_NDK_ADAPTER_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_OPEN_NDK_ADAPTER_PARAMETERS, *PNDIS_OPEN_NDK_ADAPTER_PARAMETERS
---

# _NDIS_OPEN_NDK_ADAPTER_PARAMETERS structure


## -description


The <b>NDIS_OPEN_NDK_ADAPTER_PARAMETERS</b> structure specifies parameters to open an NDK adapter instance on the NDK-capable miniport adapter.


## -syntax


````
typedef struct _NDIS_OPEN_NDK_ADAPTER_PARAMETERS {
  NDK_VERSION Version;
} NDIS_OPEN_NDK_ADAPTER_PARAMETERS, *PNDIS_OPEN_NDK_ADAPTER_PARAMETERS;
````


## -struct-fields




### -field Version

The version of the NDK provider interface (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439942">NDK_VERSION</a>) that is to be used. 

For NDIS 6.30 (Windows Server 2012), the major version number is 1. The  minor version number is 1.

For NDIS 6.40 (Windows Server 2012 R2), the major version number is 1. The  minor version number is 2.


### -field SwitchId

 


### -field VPortId

 



## -remarks


To open an NDK adapter, NDIS calls the <a href="..\ndisndk\nc-ndisndk-open_ndk_adapter_handler.md">OPEN_NDK_ADAPTER_HANDLER</a> function and passes it a  pointer to an <b>NDIS_OPEN_NDK_ADAPTER_PARAMETERS</b> structure that defines the NDK adapter open parameters.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439942">NDK_VERSION</a>

<a href="..\ndisndk\nc-ndisndk-open_ndk_adapter_handler.md">OPEN_NDK_ADAPTER_HANDLER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_OPEN_NDK_ADAPTER_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

