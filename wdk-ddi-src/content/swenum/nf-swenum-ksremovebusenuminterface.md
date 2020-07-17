---
UID: NF:swenum.KsRemoveBusEnumInterface
title: KsRemoveBusEnumInterface function (swenum.h)
description: The KsRemoveBusEnumInterface function removes an interface to the demand-load bus enumerator object.
old-location: stream\ksremovebusenuminterface.htm
tech.root: stream
ms.assetid: 4b1da622-9a48-4c18-9eee-a99830bd26af
ms.date: 04/23/2018
keywords: ["KsRemoveBusEnumInterface function"]
ms.keywords: KsRemoveBusEnumInterface, KsRemoveBusEnumInterface function [Streaming Media Devices], ksfunc_cf6401bc-80bf-4678-80f9-89c23b333bdc.xml, stream.ksremovebusenuminterface, swenum/KsRemoveBusEnumInterface
f1_keywords:
 - "swenum/KsRemoveBusEnumInterface"
 - "KsRemoveBusEnumInterface"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsRemoveBusEnumInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsRemoveBusEnumInterface function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsRemoveBusEnumInterface</b> function removes an interface to the demand-load bus enumerator object. 


## -parameters




### -param Irp [in]

Pointer to an IRP that contains a SWENUM_INSTALL_INTERFACE structure that specifies the device ID, interface ID, and reference string of the specific device and interface to be removed. For information about this structure, see theRemarks section below.


## -returns



Returns STATUS_SUCCESS if successful. Otherwise, it returns an appropriate error code.




## -remarks



The <b>Irp->AssociatedIrp.SystemBuffer</b> is assumed to contain a SWENUM_INSTALL_INTERFACE structure. The <i>DeviceId</i>, <i>InterfaceId</i> and <i>ReferenceString</i> members of the structure specify the specific device and interface to be removed.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/swenum/nf-swenum-ksinstallbusenuminterface">KsInstallBusEnumInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/swenum/ns-swenum-_swenum_install_interface">SWENUM_INSTALL_INTERFACE</a>
 

 

