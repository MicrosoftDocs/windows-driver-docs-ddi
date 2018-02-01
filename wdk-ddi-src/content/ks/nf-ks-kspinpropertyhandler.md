---
UID: NF:ks.KsPinPropertyHandler
title: KsPinPropertyHandler function
author: windows-driver-content
description: The KsPinPropertyHandler function performs standard handling of the static members of the KSPROPSETID_Pin property set. This handling does not include KSPROPERTY_PIN_CINSTANCES or KSPROPERTY_PIN_DATAINTERSECTION.
old-location: stream\kspinpropertyhandler.htm
old-project: stream
ms.assetid: b721b79b-93f3-4dc8-853d-543222464341
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsPinPropertyHandler, ksfunc_4ebda111-4b9a-4e8e-b050-af336121bcf0.xml, ks/KsPinPropertyHandler, stream.kspinpropertyhandler, KsPinPropertyHandler function [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
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
-	KsPinPropertyHandler
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinPropertyHandler function


## -description


The <b>KsPinPropertyHandler</b> function performs standard handling of the static members of<b> the </b><a href="https://msdn.microsoft.com/library/windows/hardware/ff566584">KSPROPSETID_Pin</a> property set. This handling does not include <a href="https://msdn.microsoft.com/library/windows/hardware/ff565193">KSPROPERTY_PIN_CINSTANCES</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff565198">KSPROPERTY_PIN_DATAINTERSECTION</a>. 


## -syntax


````
NTSTATUS KsPinPropertyHandler(
  _In_          PIRP             Irp,
  _In_          PKSPROPERTY      Property,
  _Inout_       PVOID            Data,
  _In_          ULONG            DescriptorsCount,
  _In_    const KSPIN_DESCRIPTOR *Descriptor
);
````


## -parameters




### -param Irp [in]

Specifies the IRP handling the connection request.


### -param Property [in]

Specifies the specific property information.


### -param Data [in, out]

Specifies the data parameter mapped to a system address. This is the same parameter passed to a property handler through a <a href="..\ks\nf-ks-kspropertyhandler.md">KsPropertyHandler</a> callback.


### -param DescriptorsCount [in]

Specifies the number of pin descriptors being passed.


### -param Descriptor [in]

Specifies the pointer to the list of pin descriptors.


## -returns


The <b>KsPinPropertyHandler</b> function returns STATUS_SUCCESS or an error specific to the property being handled. The function fills in the IO_STATUS_BLOCK.Information field of the PIRP.IoStatus element within the IRP. It does not set the IO_STATUS_BLOCK.Status field nor complete the IRP.



## -remarks


Do not use the <b>KsPinPropertyHandler</b> function to define a pin property set; a pin property set can be more easily defined using the DEFINE_KSPROPERY_PINSET macro.


