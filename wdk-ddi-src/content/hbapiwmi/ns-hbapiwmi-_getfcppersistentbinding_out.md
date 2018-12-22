---
UID: NS:hbapiwmi._GetFcpPersistentBinding_OUT
title: "_GetFcpPersistentBinding_OUT"
description: The GetFcpPersistentBinding_OUT structure is used to report the output parameter data of the GetFcpPersistentBinding WMI method to the WMI client.
old-location: storage\getfcppersistentbinding_out.htm
tech.root: storage
ms.assetid: 1bb7c529-df26-4173-a098-6a19adf6b569
ms.date: 03/29/2018
ms.keywords: "*PGetFcpPersistentBinding_OUT, GetFcpPersistentBinding_OUT, GetFcpPersistentBinding_OUT structure [Storage Devices], PGetFcpPersistentBinding_OUT, PGetFcpPersistentBinding_OUT structure pointer [Storage Devices], _GetFcpPersistentBinding_OUT, hbapiwmi/GetFcpPersistentBinding_OUT, hbapiwmi/PGetFcpPersistentBinding_OUT, storage.getfcppersistentbinding_out, structs-Fibre_6deac9e1-fd5f-4bc1-9349-39bc61c4c6bb.xml"
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
-	GetFcpPersistentBinding_OUT
product:
- Windows
targetos: Windows
req.typenames: GetFcpPersistentBinding_OUT, *PGetFcpPersistentBinding_OUT
---

# _GetFcpPersistentBinding_OUT structure


## -description


The GetFcpPersistentBinding_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553966">GetFcpPersistentBinding</a> WMI method to the WMI client.


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see HBA_STATUS.


### -field TotalEntryCount

Indicates the total number of persistent bindings retrieved by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553966">GetFcpPersistentBinding</a> WMI method.


### -field OutEntryCount

Indicates the total number of mappings retrieved by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554948">GetFcpTargetMapping</a> WMI method. This value will be less than or equal to <b>TotalEntryCount</b>.


### -field Entry

Contains an array of structures of type HBAFCPBindingEntry that describe an HBA's bindings between operating system and fibre channel protocol (FCP) identifiers.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff553966">GetFcpPersistentBinding</a> WMI method retrieves the bindings between SCSI and fibre channel protocol (FCP) identifiers for the logical units.

The WMI tool suite generates a declaration of the GetFcpPersistentBinding_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553966">GetFcpPersistentBinding</a>
 

 

