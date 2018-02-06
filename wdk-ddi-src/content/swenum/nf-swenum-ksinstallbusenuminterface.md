---
UID: NF:swenum.KsInstallBusEnumInterface
title: KsInstallBusEnumInterface function
author: windows-driver-content
description: The KsInstallBusEnumInterface function installs an interface to the demand-load bus enumerator object.
old-location: stream\ksinstallbusenuminterface.htm
old-project: stream
ms.assetid: d9703786-c46e-4466-a229-9ed0348cb45e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ksinstallbusenuminterface, ksfunc_6c26cb96-610b-4030-9f9b-ef878fdfe086.xml, KsInstallBusEnumInterface function [Streaming Media Devices], swenum/KsInstallBusEnumInterface, KsInstallBusEnumInterface
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsInstallBusEnumInterface
product: Windows
targetos: Windows
req.typenames: "*PSTREAM_TIME_REFERENCE, STREAM_TIME_REFERENCE"
req.product: Windows 10 or later.
---

# KsInstallBusEnumInterface function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsInstallBusEnumInterface</b> function installs an interface to the demand-load bus enumerator object. 


## -syntax


````
NTSTATUS KsInstallBusEnumInterface(
  _In_ PIRP Irp
);
````


## -parameters




### -param Irp [in]

Pointer to an IRP that contains a SWENUM_INSTALL_INTERFACE structure that specifies the demand-load bus enumerator object interface to install. For information about this structure, see the Remarks section below.


## -returns


Returns STATUS_SUCCESS if successful. Otherwise, it returns an error code.



## -remarks


The <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> is assumed to contain a SWENUM_INSTALL_INTERFACE structure. The <i>DeviceId</i>, <i>InterfaceId</i> and <i>ReferenceString</i> members of the structure specify the specific device and interface with which to access this new interface. When the interface is registered with Plug and Play for the interface GUID and the associated reference string is accessed the first time through IRP_MJ_CREATE, the device will be enumerated using the format of <i>bus-identifier-prefix\device-id-GUID-string</i>. For example, SW\{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}.



## -see-also

<a href="..\swenum\ns-swenum-_swenum_install_interface.md">SWENUM_INSTALL_INTERFACE</a>

<a href="..\swenum\nf-swenum-ksremovebusenuminterface.md">KsRemoveBusEnumInterface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsInstallBusEnumInterface function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

