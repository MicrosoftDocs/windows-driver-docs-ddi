---
UID: NS:wudfddi._UMDF_IO_TARGET_OPEN_PARAMS
title: "_UMDF_IO_TARGET_OPEN_PARAMS"
author: windows-driver-content
description: The UMDF_IO_TARGET_OPEN_PARAMS structure contains file-open parameters.
old-location: wdf\umdf_io_target_open_params.htm
old-project: wdf
ms.assetid: ee8c3585-4e27-4b53-99d8-0af0c5a0099d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wudfddi/PUMDF_IO_TARGET_OPEN_PARAMS, PUMDF_IO_TARGET_OPEN_PARAMS, umdf.umdf_io_target_open_params, PUMDF_IO_TARGET_OPEN_PARAMS structure pointer, UMDF_IO_TARGET_OPEN_PARAMS structure, umdfstructs_ac731d61-3f97-4c2c-a9af-0a2a58774766.xml, _UMDF_IO_TARGET_OPEN_PARAMS, *PUMDF_IO_TARGET_OPEN_PARAMS, wdf.umdf_io_target_open_params, UMDF_IO_TARGET_OPEN_PARAMS, wudfddi/UMDF_IO_TARGET_OPEN_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
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
-	Wudfddi.h
apiname:
-	UMDF_IO_TARGET_OPEN_PARAMS
product: Windows
targetos: Windows
req.typenames: UMDF_IO_TARGET_OPEN_PARAMS, *PUMDF_IO_TARGET_OPEN_PARAMS
req.product: Windows 10 or later.
---

# _UMDF_IO_TARGET_OPEN_PARAMS structure


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>UMDF_IO_TARGET_OPEN_PARAMS</b> structure contains file-open parameters.


## -syntax


````
typedef struct _UMDF_IO_TARGET_OPEN_PARAMS {
  DWORD dwShareMode;
  DWORD dwCreationDisposition;
  DWORD dwFlagsAndAttributes;
} UMDF_IO_TARGET_OPEN_PARAMS, *PUMDF_IO_TARGET_OPEN_PARAMS;
````


## -struct-fields




### -field dwShareMode

The type of sharing to allow for the file. For more information about this member, see the <i>dwShareMode</i> parameter of <a href="http://go.microsoft.com/fwlink/p/?linkid=152795">CreateFile</a> in the Windows SDK.


### -field dwCreationDisposition

The action to take if the file already exists. For more information about this member, see the <i>dwCreationDisposition</i> parameter of <a href="http://go.microsoft.com/fwlink/p/?linkid=152795">CreateFile</a> in the Windows SDK.


### -field dwFlagsAndAttributes

Additional flags and attributes for the file. For more information about this member, see the <i>dwFlagsAndAttributes</i> parameter of <a href="http://go.microsoft.com/fwlink/p/?linkid=152795">CreateFile</a> in the Windows SDK.


## -remarks


The <b>UMDF_IO_TARGET_OPEN_PARAMS</b> structure is used as input to <a href="https://msdn.microsoft.com/library/windows/hardware/ff560273">IWDFRemoteTarget::OpenFileByName</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560276">IWDFRemoteTarget::OpenRemoteInterface</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560276">IWDFRemoteTarget::OpenRemoteInterface</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560273">IWDFRemoteTarget::OpenFileByName</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20UMDF_IO_TARGET_OPEN_PARAMS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

