---
UID: NF:wdm.ClfsMgmtHandleLogFileFull
title: ClfsMgmtHandleLogFileFull function (wdm.h)
description: The ClfsMgmtHandleLogFileFull routine attempts to make more space available in a log. It might make more space available by adding containers to the log, or it might ask clients to move their log tails.
tech.root: kernel
ms.date: 12/09/2022
keywords: ["ClfsMgmtHandleLogFileFull function"]
ms.keywords: ClfsMgmtHandleLogFileFull, ClfsMgmtHandleLogFileFull routine [Kernel-Mode Driver Architecture], Clfs_management_244be38f-f0dc-45db-b0c2-ccdee1290840.xml, kernel.clfsmgmthandlelogfilefull, wdm/ClfsMgmtHandleLogFileFull
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: IRQL <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ClfsMgmtHandleLogFileFull
 - wdm/ClfsMgmtHandleLogFileFull
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Clfs.sys
 - Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
 - ClfsMgmtHandleLogFileFull
---

## -description

The **ClfsMgmtHandleLogFileFull** routine attempts to make more space available in a log. It might make more space available by adding containers to the log, or it might ask clients to move their log tails.

## -parameters

### -param Client [in]

The client that is requesting CLFS management to make space available in the log. The value of this parameter should be the **CLFS_MGMT_CLIENT** structure that is obtained through a call to the [ClfsMgmtRegisterManagedClient](/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsmgmtregistermanagedclient) routine.

## -returns

The **ClfsMgmtHandleLogFileFull** routine returns one of the following NTSTATUS values:

| Return code | Description |
|---|---|
| **STATUS_INVALID_PARAMETER** | The client is not managing a log. |
| **STATUS_INVALID_PARAMETER_1** | The value that was supplied for the *Client* parameter either was **NULL** or does not represent a valid client. |
| **STATUS_LOG_FULL_HANDLER_IN_PROGRESS** | CLFS management is already attempting to resolve a log file full condition for this client. |
| **STATUS_UNSUCCESSFUL** | CLFS management was not able to process the request. |
| **STATUS_PENDING** | CLFS management is processing the request to create space in the log. |
| **STATUS_SUCCESS** | The requested amount of space is available in the log. |

## -remarks

To make more space available in the log, the **ClfsMgmtHandleLogFileFull** routine first tries to add more containers to the log in accordance with the growth rate, new container size, and maximum size policies. If more containers cannot be added, then the **ClfsMgmtHandleLogFileFull** routine tries to free existing space by invoking one or more clients' [ClfsAdvanceTailCallback](/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_advance_tail_callback) functions.

If the **ClfsMgmtHandleLogFileFull** routine returns STATUS_PENDING, the client's [ClfsLogGrowthCompleteCallback](/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback) function will be called when the request to make space in the log has been completed.

If the **ClfsMgmtHandleLogFileFull** routine returns STATUS_LOG_FULL_HANDLER_IN_PROGRESS, the client has already requested CLFS management to handle a log file full condition. The client's [ClfsLogGrowthCompleteCallback](/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback) function will not be called a second time.

If the **ClfsMgmtHandleLogFileFull** routine returns STATUS_SUCCESS, the call completed synchronously, and the client's [ClfsLogGrowthCompleteCallback](/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback) function will not be invoked.

If the **ClfsMgmtHandleLogFileFull** routine returns STATUS_PENDING, then CLFS management is in the process of trying to free space in the log, and will call the client's [ClfsLogGrowthCompleteCallback](/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback) function when the log file full condition has been handled. If the log is pinned, CLFS management will call the client's *ClfsLogGrowthCompleteCallback* function with the *LogIsPinned* parameter set to **TRUE** before the **ClfsMgmtHandleLogFileFull** routine returns STATUS_PENDING.

It is possible that the client's [ClfsLogGrowthCompleteCallback](/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback) function could be called before the call to **ClfsMgmtHandleLogFileFull** returns.

If the **ClfsMgmtHandleLogFileFull** routine returns STATUS_PENDING, you should not call the **ClfsMgmtHandleLogFileFull** routine again for this client until the client's [ClfsLogGrowthCompleteCallback](/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback) function has been called.

## -see-also

[ClfsAdvanceTailCallback](/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_advance_tail_callback)

[ClfsLogGrowthCompleteCallback](/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback)

[ClfsMgmtRegisterManagedClient](/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsmgmtregistermanagedclient)
