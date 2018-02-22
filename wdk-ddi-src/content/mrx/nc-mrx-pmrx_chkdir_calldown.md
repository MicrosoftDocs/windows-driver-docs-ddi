---
UID: NC:mrx.PMRX_CHKDIR_CALLDOWN
title: PMRX_CHKDIR_CALLDOWN
author: windows-driver-content
description: TheMRxIsValidDirectory routine is called by RDBSS to request that a network mini-redirector check for the existence of a remote directory.
old-location: ifsk\mrxisvaliddirectory.htm
old-project: ifsk
ms.assetid: c52441d8-b273-4e1f-b251-2b35afeda55d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.mrxisvaliddirectory, MRxIsValidDirectory, MRxIsValidDirectory routine [Installable File System Drivers], MRxIsValidDirectory, PMRX_CHKDIR_CALLDOWN, PMRX_CHKDIR_CALLDOWN, mrx/MRxIsValidDirectory, mrxref_85038658-4d92-4a54-99f1-082fbc61224d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	mrx.h
apiname:
-	MRxIsValidDirectory
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---

# PMRX_CHKDIR_CALLDOWN callback


## -description


The<i>MRxIsValidDirectory</i> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector check for the existence of a remote directory. 


## -prototype


````
PMRX_CHKDIR_CALLDOWN MRxIsValidDirectory;

NTSTATUS MRxIsValidDirectory(
  _Inout_ PRX_CONTEXT     RxContext,
  _In_    PUNICODE_STRING DirectoryName
)
{ ... }
````


## -parameters




### -param RxContext [in, out]

A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation. 


### -param DirectoryName [in]

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



<i>MRxIsValidDirectory</i> is called as part of create or open request processing for the remaining name string beyond the V_NET_ROOT structure, if the <b>IrpSp-&gt;Parameters.Create.Options</b> member has the FILE_CREATE_TREE_CONNECTION bit set on. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550805">MRxSetSdInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550773">MRxQueryQuotaInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550790">MRxSetFileInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550770">MRxQueryFileInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550796">MRxSetFileInfoAtCleanup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550810">MRxSetVolumeInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550759">MRxQueryEaInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550776">MRxQuerySdInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550755">MRxQueryDirectory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550786">MRxSetEaInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550800">MRxSetQuotaInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550782">MRxQueryVolumeInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PMRX_CHKDIR_CALLDOWN routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

