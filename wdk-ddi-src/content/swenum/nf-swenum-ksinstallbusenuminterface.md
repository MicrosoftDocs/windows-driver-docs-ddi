---
UID: NF:swenum.KsInstallBusEnumInterface
title: KsInstallBusEnumInterface function (swenum.h)
description: The KsInstallBusEnumInterface function installs an interface to the demand-load bus enumerator object.
old-location: stream\ksinstallbusenuminterface.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsInstallBusEnumInterface function"]
ms.keywords: KsInstallBusEnumInterface, KsInstallBusEnumInterface function [Streaming Media Devices], ksfunc_6c26cb96-610b-4030-9f9b-ef878fdfe086.xml, stream.ksinstallbusenuminterface, swenum/KsInstallBusEnumInterface
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KsInstallBusEnumInterface
 - swenum/KsInstallBusEnumInterface
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsInstallBusEnumInterface
---

# KsInstallBusEnumInterface function


## -description

<i>This function is intended for internal use only.</i>

The <b>KsInstallBusEnumInterface</b> function installs an interface to the demand-load bus enumerator object.

## -parameters

### -param Irp 

[in]
Pointer to an IRP that contains a SWENUM_INSTALL_INTERFACE structure that specifies the demand-load bus enumerator object interface to install. For information about this structure, see the Remarks section below.

## -returns

Returns STATUS_SUCCESS if successful. Otherwise, it returns an error code.

## -remarks

The <b>Irp->AssociatedIrp.SystemBuffer</b> is assumed to contain a SWENUM_INSTALL_INTERFACE structure. The <i>DeviceId</i>, <i>InterfaceId</i> and <i>ReferenceString</i> members of the structure specify the specific device and interface with which to access this new interface. When the interface is registered with Plug and Play for the interface GUID and the associated reference string is accessed the first time through IRP_MJ_CREATE, the device will be enumerated using the format of <i>bus-identifier-prefix\device-id-GUID-string</i>. For example, SW\{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}.

## -see-also

<a href="/windows-hardware/drivers/ddi/swenum/nf-swenum-ksremovebusenuminterface">KsRemoveBusEnumInterface</a>



<a href="/windows-hardware/drivers/ddi/swenum/ns-swenum-_swenum_install_interface">SWENUM_INSTALL_INTERFACE</a>
