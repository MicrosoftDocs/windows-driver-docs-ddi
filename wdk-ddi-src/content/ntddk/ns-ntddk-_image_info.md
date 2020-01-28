---
UID: NS:ntddk._IMAGE_INFO
title: _IMAGE_INFO (ntddk.h)
description: Used by driver's load-image routine (PLOAD_IMAGE_NOTIFY_ROUTINE) to specify image information.
old-location: kernel\image_info.htm
tech.root: kernel
ms.assetid: D2CD2457-8DDF-4449-9DC1-F1E7472C87CA
ms.date: 07/08/2019
ms.keywords: "*PIMAGE_INFO, IMAGE_INFO, IMAGE_INFO structure [Kernel-Mode Driver Architecture], PIMAGE_INFO, PIMAGE_INFO structure pointer [Kernel-Mode Driver Architecture], _IMAGE_INFO, kernel.image_info, ntddk/IMAGE_INFO, ntddk/PIMAGE_INFO"
f1_keywords:
 - "ntddk/IMAGE_INFO"
req.header: ntddk.h
req.include-header: Ntddk.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddk.h
api_name:
- IMAGE_INFO
product:
- Windows
targetos: Windows
req.typenames: IMAGE_INFO, *PIMAGE_INFO
---

# _IMAGE_INFO structure

## -description

The IMAGE_INFO structure is used by driver's load-image routine ([PLOAD_IMAGE_NOTIFY_ROUTINE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pload_image_notify_routine)) to specify load image information.

## -struct-fields

### -field Properties

Represents all the bit values within the ```struct``` that **Properties** is unioned with.

### -field ImageAddressingMode

Always set to IMAGE_ADDRESSING_MODE_32BIT.

### -field SystemModeImage

Set either to one for newly loaded kernel-mode components, such as drivers, or to zero for images that are mapped into user space.

### -field ImageMappedToAllPids

Always set to zero.

### -field ExtendedInfoPresent

If the **ExtendedInfoPresent** flag is set, IMAGE_INFO is a part of [IMAGE_INFO_EX](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_image_info_ex). Added in Windows Vista.

### -field MachineTypeMismatch

Always set to zero. Added in Windows 8/Windows Server 2012.

### -field ImageSignatureLevel

The level of signature with which code integrity has labeled the image. This value is one of the ```#define SE_SIGNING_LEVEL_*``` constants in *ntddk.h*. Added in Windows 8.1/Windows Server 2012 R2.

### -field ImageSignatureType

The type of signature with which code integrity has labeled the image. This value is a **SE_IMAGE_SIGNATURE_TYPE** enumeration value,  defined in *ntddk.h*. Added in Windows 8.1/Windows Server 2012 R2.

### -field ImagePartialMap

This value is non-zero if the image mapping view called out for is a partial view that does not map the entire image; 0 if the view maps the entire image. Added in Windows 10/Windows Server 2016.

### -field Reserved

Always set to zero.

### -field ImageBase

Set to the virtual base address of the image.

### -field ImageSelector

Always set to zero.

### -field ImageSize

Set to the virtual size, in bytes, of the image.

### -field ImageSectionNumber

Always set to zero.

## -remarks

If the **ExtendedInfoPresent** flag is set, the IMAGE_INFO structure is part of IMAGE_INFO_EX, which is a larger, extended version of the image information structure. In this case, the load-image notify routine can use the **CONTAINING_RECORD** macro (in *miniport.h*) to obtain the base address of the IMAGE_INFO_EX structure.

## -see-also

[IMAGE_INFO_EX](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_image_info_ex)

[PLOAD_IMAGE_NOTIFY_ROUTINE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pload_image_notify_routine)

[PsSetLoadImageNotifyRoutine](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetloadimagenotifyroutine)
