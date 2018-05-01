---
UID: NS:wudfddi._UMDF_IO_TARGET_OPEN_PARAMS
title: "_UMDF_IO_TARGET_OPEN_PARAMS"
author: windows-driver-content
description: The UMDF_IO_TARGET_OPEN_PARAMS structure contains file-open parameters.
old-location: wdf\umdf_io_target_open_params.htm
old-project: wdf
ms.assetid: ee8c3585-4e27-4b53-99d8-0af0c5a0099d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PUMDF_IO_TARGET_OPEN_PARAMS, PUMDF_IO_TARGET_OPEN_PARAMS, PUMDF_IO_TARGET_OPEN_PARAMS structure pointer, UMDF_IO_TARGET_OPEN_PARAMS, UMDF_IO_TARGET_OPEN_PARAMS structure, _UMDF_IO_TARGET_OPEN_PARAMS, umdf.umdf_io_target_open_params, umdfstructs_ac731d61-3f97-4c2c-a9af-0a2a58774766.xml, wdf.umdf_io_target_open_params, wudfddi/PUMDF_IO_TARGET_OPEN_PARAMS, wudfddi/UMDF_IO_TARGET_OPEN_PARAMS"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wudfddi.h
api_name:
-	UMDF_IO_TARGET_OPEN_PARAMS
product: Windows
targetos: Windows
req.typenames: UMDF_IO_TARGET_OPEN_PARAMS, *PUMDF_IO_TARGET_OPEN_PARAMS
---

# _UMDF_IO_TARGET_OPEN_PARAMS structure


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>UMDF_IO_TARGET_OPEN_PARAMS</b> structure contains file-open parameters.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560273">IWDFRemoteTarget::OpenFileByName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560276">IWDFRemoteTarget::OpenRemoteInterface</a>
 

 

