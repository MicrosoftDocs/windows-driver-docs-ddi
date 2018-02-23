---
UID: NS:video._VPOSVERSIONINFO
title: "_VPOSVERSIONINFO"
author: windows-driver-content
description: The VPOSVERSIONINFO structure contains version information about the currently running operating system.
old-location: display\vposversioninfo.htm
old-project: display
ms.assetid: b6335df5-81d9-4a00-8e97-0ebebb987d32
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: VPOSVERSIONINFO, video/PVPOSVERSIONINFO, *PVPOSVERSIONINFO, display.vposversioninfo, _VPOSVERSIONINFO, PVPOSVERSIONINFO structure pointer [Display Devices], VPOSVERSIONINFO structure [Display Devices], Video_Structs_893105be-4f14-4903-aae1-85ffe8ef8a2b.xml, video/VPOSVERSIONINFO, PVPOSVERSIONINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	video.h
apiname:
-	VPOSVERSIONINFO
product: Windows
targetos: Windows
req.typenames: VPOSVERSIONINFO, *PVPOSVERSIONINFO
req.product: Windows 10 or later.
---

# _VPOSVERSIONINFO structure


## -description


The VPOSVERSIONINFO structure contains version information about the currently running operating system.


## -syntax


````
typedef struct _VPOSVERSIONINFO {
  IN ULONG   Size;
  OUT ULONG  MajorVersion;
  OUT ULONG  MinorVersion;
  OUT ULONG  BuildNumber;
  OUT USHORT ServicePackMajor;
  OUT USHORT ServicePackMinor;
} VPOSVERSIONINFO, *PVPOSVERSIONINFO;
````


## -struct-fields




### -field Size

Specifies the size, in bytes, of the VPOSVERSIONINFO structure.


### -field MajorVersion

Specifies the major version number of the operating system. For example, for Windows 2000, the major version number is five. For Windows XP, the major version number is six.


### -field MinorVersion

Specifies the minor version number of the operating system. For example, for Windows 2000, the minor version number is zero.


### -field BuildNumber

Specifies the build number of the operating system.


### -field ServicePackMajor

Specifies the major version number of the latest Service Pack installed on the operating system. For example, for Service Pack 3, the major version number is three.


### -field ServicePackMinor

Specifies the minor version number of the latest Service Pack installed on the operating system. For example, for Service Pack 3, the minor version number is zero.


## -remarks



This structure is available in Windows XP and later.

To obtain version information about the currently running operating system, a video miniport driver would call the <a href="..\video\nf-video-videoportgetversion.md">VideoPortGetVersion</a> function, which fills in this structure.




## -see-also

<a href="..\video\nf-video-videoportgetversion.md">VideoPortGetVersion</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VPOSVERSIONINFO structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

