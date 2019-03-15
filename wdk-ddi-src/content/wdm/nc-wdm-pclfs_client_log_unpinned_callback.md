---
UID: NC:wdm.PCLFS_CLIENT_LOG_UNPINNED_CALLBACK
title: PCLFS_CLIENT_LOG_UNPINNED_CALLBACK (wdm.h)
description: The ClfsLogUnpinnedCallback function implements any actions that the client will take when a log that had previously been pinned becomes unpinned.
old-location: kernel\clfslogunpinnedcallback.htm
tech.root: kernel
ms.assetid: f28a1ad6-4946-4d1e-b430-2cdee3dfd835
ms.date: 04/30/2018
ms.keywords: ClfsLogUnpinnedCallback, ClfsLogUnpinnedCallback callback function [Kernel-Mode Driver Architecture], Clfs_management_e82832a3-b4b9-48c7-a706-9d489a55f728.xml, PCLFS_CLIENT_LOG_UNPINNED_CALLBACK, PCLFS_CLIENT_LOG_UNPINNED_CALLBACK callback, kernel.clfslogunpinnedcallback, wdm/ClfsLogUnpinnedCallback
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.irql: Called at IRQL <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- ClfsLogUnpinnedCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCLFS_CLIENT_LOG_UNPINNED_CALLBACK callback function


## -description


The <i>ClfsLogUnpinnedCallback</i> function implements any actions that the client will take when a log that had previously been pinned becomes unpinned.


## -parameters




### -param LogFile [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a> structure that represents the CLFS log stream whose tail has become unpinned.


### -param ClientData [in]

A pointer to client-supplied information. You specify this data in the <b>LogUnpinnedCallbackData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541841">CLFS_MGMT_CLIENT_REGISTRATION</a> structure.


## -returns



None




## -remarks



If a client called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541627">ClfsMgmtHandleLogFileFull</a> routine and CLFS management subsequently called the client's <a href="https://msdn.microsoft.com/library/windows/hardware/ff541562">ClfsLogGrowthCompleteCallback</a> function with a value of <b>TRUE</b> for the <i>LogIsPinned</i> parameter, then the <i>ClfsLogUnpinnedCallback</i> function will be invoked when the log becomes unpinned. 

When a client uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541642">ClfsMgmtRegisterManagedClient</a> routine to register with CLFS management, the client provides both a pointer to the <i>ClfsLogUnpinnedCallback</i> function and the custom data that will be passed as a parameter to the <i>ClfsLogUnpinnedCallback</i> function when this function is called.

The <i>ClfsLogUnpinnedCallback</i> function should only perform a minimal amount of processing before returning. For example, it might create and queue a work item to inform the client that it can resume processing.

The <i>ClfsLogGrowthCompleteCallback</i> function is called before the <i>ClfsLogUnpinnedCallback</i> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541841">CLFS_MGMT_CLIENT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541627">ClfsMgmtHandleLogFileFull</a>
 

 

