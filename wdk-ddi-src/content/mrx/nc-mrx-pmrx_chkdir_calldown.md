---
UID: NC:mrx.PMRX_CHKDIR_CALLDOWN
title: PMRX_CHKDIR_CALLDOWN (mrx.h)
description: Learn more about the PMRX_CHKDIR_CALLDOWN callback function.
tech.root: ifsk
ms.date: 10/11/2023
keywords: ["PMRX_CHKDIR_CALLDOWN callback function"]
ms.keywords: MRxIsValidDirectory, MRxIsValidDirectory routine [Installable File System Drivers], PMRX_CHKDIR_CALLDOWN, ifsk.mrxisvaliddirectory, mrx/MRxIsValidDirectory, mrxref_85038658-4d92-4a54-99f1-082fbc61224d.xml
req.header: mrx.h
req.include-header: Mrx.h
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PMRX_CHKDIR_CALLDOWN
 - mrx/PMRX_CHKDIR_CALLDOWN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_CHKDIR_CALLDOWN
---

# PMRX_CHKDIR_CALLDOWN callback function

## -description

The**MRxIsValidDirectory** routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector check for the existence of a remote directory.

## -parameters

### -param RxContext [in, out]

A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation.

### -param DirectoryName [in]

A pointer to a Unicode string that contains the name of the remote directory.

## -returns

**MRxIsValidDirectory** returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following:

| Return code | Description |
| ------------- | ------------- |
| STATUS_BAD_NETWORK_PATH | This remote directory does not exist. |

## -remarks

**MRxIsValidDirectory** is called as part of create or open request processing for the remaining name string beyond the V_NET_ROOT structure, if the **IrpSp->Parameters.Create.Options** member has the FILE_CREATE_TREE_CONNECTION bit set on.

## -see-also

[**MRxQueryDirectory**](/windows-hardware/drivers/ifs/mrxquerydirectory)

[**MRxQueryEaInfo**](/windows-hardware/drivers/ifs/mrxqueryeainfo)

[**MRxQueryFileInfo**](/windows-hardware/drivers/ifs/mrxqueryfileinfo)

[**MRxQueryQuotaInfo**](/windows-hardware/drivers/ifs/mrxqueryquotainfo)

[**MRxQuerySdInfo**](/windows-hardware/drivers/ifs/mrxquerysdinfo)

[**MRxQueryVolumeInfo**](/windows-hardware/drivers/ifs/mrxqueryvolumeinfo)

[**MRxSetEaInfo**](/windows-hardware/drivers/ifs/mrxseteainfo)

[**MRxSetFileInfo**](/windows-hardware/drivers/ifs/mrxsetfileinfo)

[**MRxSetFileInfoAtCleanup**](/windows-hardware/drivers/ifs/mrxsetfileinfoatcleanup)

[**MRxSetQuotaInfo**](/windows-hardware/drivers/ifs/mrxsetquotainfo)

[**MRxSetSdInfo**](/windows-hardware/drivers/ifs/mrxsetsdinfo)

[**MRxSetVolumeInfo**](/windows-hardware/drivers/ifs/mrxsetvolumeinfo)
