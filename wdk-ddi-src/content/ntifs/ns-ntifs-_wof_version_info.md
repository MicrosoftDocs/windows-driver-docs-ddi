---
UID: NS:ntifs._WOF_VERSION_INFO
title: "_WOF_VERSION_INFO"
author: windows-driver-content
description: The WOF_VERSION_INFO structure contains the version corresponding to the driver supporting a given provider.
old-location: ifsk\wof_version_info.htm
old-project: ifsk
ms.assetid: 953F34FC-2E8F-4569-89B8-2F9541456F3B
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: WOF_VERSION_INFO structure [Installable File System Drivers], ntifs/WOF_VERSION_INFO, *PWOF_VERSION_INFO, PWOF_VERSION_INFO structure pointer [Installable File System Drivers], WOF_VERSION_INFO, _WOF_VERSION_INFO, PWOF_VERSION_INFO, ifsk.wof_version_info, ntifs/PWOF_VERSION_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntifs.h
apiname:
-	WOF_VERSION_INFO
product: Windows
targetos: Windows
req.typenames: "*PWOF_VERSION_INFO, WOF_VERSION_INFO"
---

# _WOF_VERSION_INFO structure


## -description


The <b>WOF_VERSION_INFO</b> structure contains the version corresponding to the driver supporting a given provider.


## -syntax


````
typedef struct _WOF_VERSION_INFO {
  ULONG WofVersion;
} WOF_VERSION_INFO, *PWOF_VERSION_INFO;
````


## -struct-fields




### -field WofVersion

The version of the WOF driver. This value includes the major and minor version numbers of the operating system in the high-order word, and the build number of the operating system in the low-order word. The major version can be extracted with HIBYTE(HIWORD(<i>WofVersion</i>)); the minor version can be extracted with LOBYTE(HIWORD(<i>WofVersion</i>)); the build number can be extracted with LOWORD(<i>WofVersion</i>). 


## -see-also

<a href="..\ntifs\ns-ntifs-_wof_external_file_id.md">WOF_EXTERNAL_FILE_ID</a>



<a href="..\ntifs\ns-ntifs-_wof_external_info.md">WOF_EXTERNAL_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt426734">FSCTL_GET_WOF_VERSION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20WOF_VERSION_INFO structure%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

