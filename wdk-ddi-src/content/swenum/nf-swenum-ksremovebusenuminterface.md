---
UID: NF:swenum.KsRemoveBusEnumInterface
title: KsRemoveBusEnumInterface function
author: windows-driver-content
description: The KsRemoveBusEnumInterface function removes an interface to the demand-load bus enumerator object.
old-location: stream\ksremovebusenuminterface.htm
old-project: stream
ms.assetid: 4b1da622-9a48-4c18-9eee-a99830bd26af
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: KsRemoveBusEnumInterface, ksfunc_cf6401bc-80bf-4678-80f9-89c23b333bdc.xml, KsRemoveBusEnumInterface function [Streaming Media Devices], stream.ksremovebusenuminterface, swenum/KsRemoveBusEnumInterface
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
-	KsRemoveBusEnumInterface
product: Windows
targetos: Windows
req.typenames: STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE
req.product: Windows 10 or later.
---

# KsRemoveBusEnumInterface function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsRemoveBusEnumInterface</b> function removes an interface to the demand-load bus enumerator object. 


## -syntax


````
NTSTATUS KsRemoveBusEnumInterface(
  _In_ PIRP Irp
);
````


## -parameters




### -param Irp [in]

Pointer to an IRP that contains a SWENUM_INSTALL_INTERFACE structure that specifies the device ID, interface ID, and reference string of the specific device and interface to be removed. For information about this structure, see theRemarks section below.


## -returns



Returns STATUS_SUCCESS if successful. Otherwise, it returns an appropriate error code.




## -remarks



The <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> is assumed to contain a SWENUM_INSTALL_INTERFACE structure. The <i>DeviceId</i>, <i>InterfaceId</i> and <i>ReferenceString</i> members of the structure specify the specific device and interface to be removed.




## -see-also

<a href="..\swenum\nf-swenum-ksinstallbusenuminterface.md">KsInstallBusEnumInterface</a>



<a href="..\swenum\ns-swenum-_swenum_install_interface.md">SWENUM_INSTALL_INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsRemoveBusEnumInterface function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

