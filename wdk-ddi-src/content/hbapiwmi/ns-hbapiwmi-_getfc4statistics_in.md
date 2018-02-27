---
UID: NS:hbapiwmi._GetFC4Statistics_IN
title: "_GetFC4Statistics_IN"
author: windows-driver-content
description: The GetFC4Statistics_IN structure is used to pass input parameter data to the GetFC4Statistics WMI method.
old-location: storage\getfc4statistics_in.htm
old-project: storage
ms.assetid: 10e3c823-97e3-47e9-8545-94cd186e5b59
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PGetFC4Statistics_IN, GetFC4Statistics_IN, GetFC4Statistics_IN structure [Storage Devices], PGetFC4Statistics_IN, PGetFC4Statistics_IN structure pointer [Storage Devices], _GetFC4Statistics_IN, hbapiwmi/GetFC4Statistics_IN, hbapiwmi/PGetFC4Statistics_IN, storage.getfc4statistics_in, structs-Fibre_17ea3e0e-1cf9-4cf8-9128-1152e610847c.xml"
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
-	GetFC4Statistics_IN
product: Windows
targetos: Windows
req.typenames: GetFC4Statistics_IN, *PGetFC4Statistics_IN
---

# _GetFC4Statistics_IN structure


## -description


The GetFC4Statistics_IN structure is used to pass input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553949">GetFC4Statistics</a> WMI method.


## -syntax


````
typedef struct _GetFC4Statistics_IN {
  UCHAR PortWWN[8];
  UCHAR FC4Type;
} GetFC4Statistics_IN, *PGetFC4Statistics_IN;
````


## -struct-fields




### -field PortWWN

Contains the worldwide name for the local port of type Nx_Port whose traffic statistics are to be reported. 


### -field FC4Type

Contains a value that indicates the type FC-4 protocol. For an explanation of FC4 types, see the T11 committee's <i>Fibre Channel Generic Services - 4 </i>specification. 


## -remarks



The method <a href="https://msdn.microsoft.com/library/windows/hardware/ff553949">GetFC4Statistics</a> queries an HBA and port of type Nx_Port for traffic statistics associated with the indicated FC-4 protocol.

The WMI tool suite generates a declaration of the GetFC4Statistics_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.

For a definition of Nx_Port, see the T11 committee's specification for <i>Fibre Channel HBA API</i> (FC-HBA).




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553949">GetFC4Statistics</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetFC4Statistics_IN structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

