---
UID: NS:ntddk._IMAGE_INFO
title: "_IMAGE_INFO"
author: windows-driver-content
description: Used by driver's load-image routine (PLOAD_IMAGE_NOTIFY_ROUTINE) to specify image information.
old-location: kernel\image_info.htm
old-project: kernel
ms.assetid: D2CD2457-8DDF-4449-9DC1-F1E7472C87CA
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.image_info, IMAGE_INFO structure [Kernel-Mode Driver Architecture], PIMAGE_INFO, PIMAGE_INFO structure pointer [Kernel-Mode Driver Architecture], IMAGE_INFO, ntddk/IMAGE_INFO, *PIMAGE_INFO, ntddk/PIMAGE_INFO, _IMAGE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddk.h
apiname:
-	IMAGE_INFO
product: Windows
targetos: Windows
req.typenames: "*PIMAGE_INFO, IMAGE_INFO"
---

# _IMAGE_INFO structure


## -description


Used by driver's load-image routine (<a href="..\ntddk\nc-ntddk-pload_image_notify_routine.md">PLOAD_IMAGE_NOTIFY_ROUTINE</a>) to specify image information.


## -syntax


````
typedef struct _IMAGE_INFO {
  union {
    ULONG Properties;
    struct {
    };
    ULONG ImageAddressingMode  :8;
    ULONG SystemModeImage  :1;
    ULONG ImageMappedToAllPids  :1;
    ULONG ExtendedInfoPresent  :1;
    ULONG MachineTypeMismatch  :1;
    ULONG ImageSignatureLevel  :4;
    ULONG ImageSignatureType  :3;
    ULONG ImagePartialMap  :1;
    ULONG Reserved  :12;
  };
  ULONG  ImageBase;
  ULONG  ImageSelector;
  SIZE_T ImageSize;
  ULONG  ImageSectionNumber;
} IMAGE_INFO, *PIMAGE_INFO;
````


## -struct-fields




### -field Properties


### -field ImageAddressingMode

Always set to IMAGE_ADDRESSING_MODE_32BIT.


### -field SystemModeImage

Set either to one for newly loaded kernel-mode components, such as drivers, or to zero for images that are mapped into user space.


### -field ImageMappedToAllPids

Always set to zero.


### -field ExtendedInfoPresent

If the <b>ExtendedInfoPresent</b> flag is set, the <b>IMAGE_INFO</b> structure is part of a larger, extended version of the image information structure (see <a href="..\ntddk\ns-ntddk-_image_info_ex.md">IMAGE_INFO_EX</a>). Added in Windows Vista. For more information, see "Extended version of the image information structure" later in this Remarks section.


### -field MachineTypeMismatch

Always set to zero. Added in Windows 8/Windows Server 2012.


### -field ImageSignatureLevel

The level of signature with which code integrity has labeled the image. This value is one of the <code>#define SE_SIGNING_LEVEL_*</code> constants in ntddk.h. Added in Windows 8.1/Windows Server 2012 R2.


### -field ImageSignatureType

The type of signature with which code integrity has labeled the image. This value is a <b>SE_IMAGE_SIGNATURE_TYPE</b> enumeration value,  defined in ntddk.h. Added in Windows 8.1/Windows Server 2012 R2.


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



If the <b>ExtendedInfoPresent</b> flag is set, the <b>IMAGE_INFO</b> structure is part of a larger, extended version of the image information structure, <a href="..\ntddk\ns-ntddk-_image_info_ex.md">IMAGE_INFO_EX</a>.




## -see-also

<a href="..\ntddk\nf-ntddk-pssetloadimagenotifyroutine.md">PsSetLoadImageNotifyRoutine</a>



<a href="..\ntddk\ns-ntddk-_image_info_ex.md">IMAGE_INFO_EX</a>



<a href="..\ntddk\nc-ntddk-pload_image_notify_routine.md">PLOAD_IMAGE_NOTIFY_ROUTINE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IMAGE_INFO structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

