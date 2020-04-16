---
UID: NS:ntddk._IMAGE_INFO_EX
title: _IMAGE_INFO_EX (ntddk.h)
description: IMAGE_INFO_EX is the extended version of the IMAGE_INFO load image information structure.
old-location: kernel\image_info_ex.htm
tech.root: kernel
ms.assetid: 97F3D9BE-9069-4A4A-B114-FC9331510512
ms.date: 07/08/2019
keywords: ["_IMAGE_INFO_EX structure"]
ms.keywords: "*PIMAGE_INFO_EX, IMAGE_INFO_EX, IMAGE_INFO_EX structure [Kernel-Mode Driver Architecture], PIMAGE_INFO_EX, PIMAGE_INFO_EX structure pointer [Kernel-Mode Driver Architecture], _IMAGE_INFO_EX, kernel.image_info_ex, ntddk/IMAGE_INFO_EX, ntddk/PIMAGE_INFO_EX"
f1_keywords:
 - "ntddk/IMAGE_INFO_EX"
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
- IMAGE_INFO_EX
product:
- Windows
targetos: Windows
req.typenames: IMAGE_INFO_EX, *PIMAGE_INFO_EX
---

# _IMAGE_INFO_EX structure

## -description

IMAGE_INFO_EX is the larger, extended version of the [IMAGE_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_image_info) load image information structure.

## -struct-fields

### -field Size

Specifies the size, in bytes, of the IMAGE_INFO_EX structure.

### -field ImageInfo

An [IMAGE_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_image_info) structure that specifies load image information.

### -field FileObject

Pointer to the file object of the backing file for the image. The driver can take a reference to this object or use it for other operations.

## -remarks

If the **ExtendedInfoPresent** flag is set in the IMAGE_INFO structure, the load image information is part of IMAGE_INFO_EX. In this case, the load-image notify routine can use the **CONTAINING_RECORD** macro (in *miniport.h*) to obtain the base address of the IMAGE_INFO_EX structure.

## -see-also

[IMAGE_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_image_info)

[PLOAD_IMAGE_NOTIFY_ROUTINE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pload_image_notify_routine)

[PsSetLoadImageNotifyRoutine](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetloadimagenotifyroutine)
