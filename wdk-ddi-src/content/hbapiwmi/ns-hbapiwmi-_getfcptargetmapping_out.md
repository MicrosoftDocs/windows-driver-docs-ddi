---
UID: NS:hbapiwmi._GetFcpTargetMapping_OUT
title: "_GetFcpTargetMapping_OUT"
author: windows-driver-content
description: The GetFcpTargetMapping_OUT structure is used to report the output parameter data of the GetFcpTargetMapping WMI method to the WMI client.
old-location: storage\getfcptargetmapping_out.htm
old-project: storage
ms.assetid: a3a3050a-6fa2-4ace-87f2-41b8364f4d30
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PGetFcpTargetMapping_OUT, GetFcpTargetMapping_OUT, GetFcpTargetMapping_OUT structure [Storage Devices], PGetFcpTargetMapping_OUT, PGetFcpTargetMapping_OUT structure pointer [Storage Devices], _GetFcpTargetMapping_OUT, hbapiwmi/GetFcpTargetMapping_OUT, hbapiwmi/PGetFcpTargetMapping_OUT, storage.getfcptargetmapping_out, structs-Fibre_ab6aca55-bb7c-4983-863c-de94e835a600.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbapiwmi.h
api_name:
-	GetFcpTargetMapping_OUT
product: Windows
targetos: Windows
req.typenames: GetFcpTargetMapping_OUT, *PGetFcpTargetMapping_OUT
---

# _GetFcpTargetMapping_OUT structure


## -description


The GetFcpTargetMapping_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554948">GetFcpTargetMapping</a> WMI method to the WMI client. 


## -syntax


````
typedef struct _GetFcpTargetMapping_OUT {
  ULONG           HBAStatus;
  ULONG           TotalEntryCount;
  ULONG           OutEntryCount;
  HBAFCPScsiEntry Entry[1];
} GetFcpTargetMapping_OUT, *PGetFcpTargetMapping_OUT;
````


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>. 


### -field TotalEntryCount

Indicates the total number of persistent bindings associated with the HBA..


### -field OutEntryCount

Indicates the total number of mappings retrieved by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554948">GetFcpTargetMapping</a> WMI method. This value will be less than or equal to <b>TotalEntryCount</b>. 


### -field Entry

Contains an array of structures of type <a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpscsientry.md">HBAFCPScsiEntry</a> that describe an HBA's bindings between operating system and fibre channel protocol (FCP) identifiers. 


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff554948">GetFcpTargetMapping</a> WMI method reports mappings between the information that uniquely identifies a set of logical units for the operating system and the fibre channel protocol (FCP) identifiers for these logical units.

The WMI tool suite generates a declaration of the GetFcpTargetMapping_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpscsientry.md">HBAFCPScsiEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554948">GetFcpTargetMapping</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetFcpTargetMapping_OUT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

