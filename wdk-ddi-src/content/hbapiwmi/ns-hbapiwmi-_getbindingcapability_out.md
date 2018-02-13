---
UID: NS:hbapiwmi._GetBindingCapability_OUT
title: "_GetBindingCapability_OUT"
author: windows-driver-content
description: The GetBindingCapability_OUT structure is used by a WMI provider to report the output parameter data of the GetBindingCapability WMI method to the WMI client.
old-location: storage\getbindingcapability_out.htm
old-project: storage
ms.assetid: c02bb43c-8f9a-470a-ba65-f3a69b5c6110
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: hbapiwmi/PGetBindingCapability_OUT, _GetBindingCapability_OUT, hbapiwmi/GetBindingCapability_OUT, structs-Fibre_611bcad6-5d7f-43ea-8202-4c19bec45f88.xml, PGetBindingCapability_OUT structure pointer [Storage Devices], *PGetBindingCapability_OUT, storage.getbindingcapability_out, GetBindingCapability_OUT, PGetBindingCapability_OUT, GetBindingCapability_OUT structure [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	hbapiwmi.h
apiname:
-	GetBindingCapability_OUT
product: Windows
targetos: Windows
req.typenames: "*PGetBindingCapability_OUT, GetBindingCapability_OUT"
---

# _GetBindingCapability_OUT structure


## -description


The GetBindingCapability_OUT structure is used by a WMI provider to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553902">GetBindingCapability</a> WMI method to the WMI client.


## -syntax


````
typedef struct _GetBindingCapability_OUT {
  ULONG HBAStatus;
  ULONG BindType;
} GetBindingCapability_OUT, *PGetBindingCapability_OUT;
````


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>. 


### -field BindType

Indicates the ability of an HBA and its miniport driver to provide a specific set of features related to persistent binding. For a list of values that this parameter can have, see the description of the HBA_BIND_TYPE WMI class qualifier.


## -remarks



The WMI tool suite generates a declaration of the GetBindingCapability_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553902">GetBindingCapability</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetBindingCapability_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

