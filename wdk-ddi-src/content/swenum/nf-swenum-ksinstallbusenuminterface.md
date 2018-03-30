---
UID: NF:swenum.KsInstallBusEnumInterface
title: KsInstallBusEnumInterface function
author: windows-driver-content
description: The KsInstallBusEnumInterface function installs an interface to the demand-load bus enumerator object.
old-location: stream\ksinstallbusenuminterface.htm
old-project: stream
ms.assetid: d9703786-c46e-4466-a229-9ed0348cb45e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsInstallBusEnumInterface, KsInstallBusEnumInterface function [Streaming Media Devices], ksfunc_6c26cb96-610b-4030-9f9b-ef878fdfe086.xml, stream.ksinstallbusenuminterface, swenum/KsInstallBusEnumInterface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: swenum.h
req.include-header: Swenum.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsInstallBusEnumInterface
product: Windows
targetos: Windows
req.typenames: STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE
req.product: Windows 10 or later.
---

# KsInstallBusEnumInterface function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsInstallBusEnumInterface</b> function installs an interface to the demand-load bus enumerator object. 


## -parameters




### -param Irp [in]

Pointer to an IRP that contains a SWENUM_INSTALL_INTERFACE structure that specifies the demand-load bus enumerator object interface to install. For information about this structure, see the Remarks section below.


## -returns



Returns STATUS_SUCCESS if successful. Otherwise, it returns an error code.




## -remarks



The <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> is assumed to contain a SWENUM_INSTALL_INTERFACE structure. The <i>DeviceId</i>, <i>InterfaceId</i> and <i>ReferenceString</i> members of the structure specify the specific device and interface with which to access this new interface. When the interface is registered with Plug and Play for the interface GUID and the associated reference string is accessed the first time through IRP_MJ_CREATE, the device will be enumerated using the format of <i>bus-identifier-prefix\device-id-GUID-string</i>. For example, SW\{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566794">KsRemoveBusEnumInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568498">SWENUM_INSTALL_INTERFACE</a>
 

 

