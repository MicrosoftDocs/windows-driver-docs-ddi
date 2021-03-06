---
UID: NF:mcd.ChangerAdditionalExtensionSize
title: ChangerAdditionalExtensionSize function (mcd.h)
description: ChangerAdditionalExtensionSize indicates the number of bytes the changer miniclass driver requires to store device-specific information in the device extension.
old-location: storage\changeradditionalextensionsize.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ChangerAdditionalExtensionSize function"]
ms.keywords: ChangerAdditionalExtensionSize, ChangerAdditionalExtensionSize function [Storage Devices], chgrmini_22c1f2f6-d441-4208-b104-46711c4204cd.xml, mcd/ChangerAdditionalExtensionSize, storage.changeradditionalextensionsize
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ChangerAdditionalExtensionSize
 - mcd/ChangerAdditionalExtensionSize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mcd.h
api_name:
 - ChangerAdditionalExtensionSize
---

# ChangerAdditionalExtensionSize function


## -description

<b>ChangerAdditionalExtensionSize</b> indicates the number of bytes the changer miniclass driver requires to store device-specific information in the device extension.

## -parameters

## -returns

<b>ChangerAdditionalExtensionSize</b> returns the size, in bytes, of the additional device extension space required by the changer miniclass driver.

## -remarks

The changer class driver calls <b>ChangerAdditionalExtensionSize</b> to determine the number of bytes the miniclass driver requires in the device extension for a particular changer before creating the device object to represent that changer.

The device-specific information stored by a changer miniclass driver is determined by the driver. It typically includes zero-based offsets that other miniclass driver routines can use to translate between device-specific element addresses and the zero-based element addresses used by the system. It can also include SCSI inquiry data or the non-SCSI equivalent.

## -see-also

<a href="/windows-hardware/drivers/ddi/mcd/nf-mcd-changerinitialize">ChangerInitialize</a>
