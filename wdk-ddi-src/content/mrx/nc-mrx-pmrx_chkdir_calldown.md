---
UID: NC:mrx.PMRX_CHKDIR_CALLDOWN
title: PMRX_CHKDIR_CALLDOWN (mrx.h)
description: TheMRxIsValidDirectory routine is called by RDBSS to request that a network mini-redirector check for the existence of a remote directory.
old-location: ifsk\mrxisvaliddirectory.htm
tech.root: ifsk
ms.assetid: c52441d8-b273-4e1f-b251-2b35afeda55d
ms.date: 04/16/2018
keywords: ["PMRX_CHKDIR_CALLDOWN callback function"]
ms.keywords: MRxIsValidDirectory, MRxIsValidDirectory routine [Installable File System Drivers], PMRX_CHKDIR_CALLDOWN, ifsk.mrxisvaliddirectory, mrx/MRxIsValidDirectory, mrxref_85038658-4d92-4a54-99f1-082fbc61224d.xml
f1_keywords:
 - "mrx/MRxIsValidDirectory"
 - "MRxIsValidDirectory"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- mrx.h
api_name:
- MRxIsValidDirectory
targetos: Windows
req.typenames: 
---

# PMRX_CHKDIR_CALLDOWN callback function


## -description


The<i>MRxIsValidDirectory</i> routine is called by <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector check for the existence of a remote directory. 


## -parameters




### -param RxContext 
[in, out]
A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation. 


### -param DirectoryName 
[in]
A pointer to a Unicode string that contains the name of the remote directory.


## -returns



<i>MRxIsValidDirectory</i> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BAD_NETWORK_PATH</b></dt>
</dl>
</td>
<td width="60%">
This remote directory does not exist. 

</td>
</tr>
</table>
 




## -remarks



<i>MRxIsValidDirectory</i> is called as part of create or open request processing for the remaining name string beyond the V_NET_ROOT structure, if the <b>IrpSp->Parameters.Create.Options</b> member has the FILE_CREATE_TREE_CONNECTION bit set on. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxquerydirectory">MRxQueryDirectory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxqueryeainfo">MRxQueryEaInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxqueryfileinfo">MRxQueryFileInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxqueryquotainfo">MRxQueryQuotaInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxquerysdinfo">MRxQuerySdInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxqueryvolumeinfo">MRxQueryVolumeInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxseteainfo">MRxSetEaInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxsetfileinfo">MRxSetFileInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxsetfileinfoatcleanup">MRxSetFileInfoAtCleanup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxsetquotainfo">MRxSetQuotaInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxsetsdinfo">MRxSetSdInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxsetvolumeinfo">MRxSetVolumeInfo</a>
 

 

