---
UID: NF:fltkernel.FltSetEcpListIntoCallbackData
title: FltSetEcpListIntoCallbackData function
author: windows-driver-content
description: The FltSetEcpListIntoCallbackData routine attaches an extra create parameter context structure (ECP) list to a create operation callback-data object.
old-location: ifsk\fltsetecplistintocallbackdata.htm
old-project: ifsk
ms.assetid: 91179c1c-fe45-418f-8992-a40e41e3017a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, D, E, F, FltApiRef_p_to_z_01e8fac7-3c58-4ed2-85ac-38580cca36e6.xml, FltSetEcpListIntoCallbackData, FltSetEcpListIntoCallbackData routine [Installable File System Drivers], I, L, S, a, b, c, e, fltkernel/FltSetEcpListIntoCallbackData, i, ifsk.fltsetecplistintocallbackdata, k, l, n, o, p, s, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltSetEcpListIntoCallbackData
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltSetEcpListIntoCallbackData function


## -description


The <b>FltSetEcpListIntoCallbackData </b>routine attaches an extra create parameter context structure (ECP) list to a create operation callback-data object.


## -syntax


````
NTSTATUS FltSetEcpListIntoCallbackData(
  _In_ PFLT_FILTER        Filter,
  _In_ PFLT_CALLBACK_DATA Data,
  _In_ PECP_LIST          EcpList
);
````


## -parameters




### -param Filter [in]

Opaque filter pointer to the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param CallbackData

TBD


### -param EcpList [in]

Pointer to the ECP list, which contains one or more ECPs, to be attached to the callback-data object.


#### - Data [in]

Pointer to a callback-data object of type <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>, which represents the create operation.


## -returns



<b>FltSetEcpListIntoCallbackData </b>returns one of the following NTSTATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The given ECP list was successfully attached to the given callback-data object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The given callback data object was not an IRP-based create operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_3</b></dt>
</dl>
</td>
<td width="60%">
An ECP list has already been attached to the given callback-data object.

</td>
</tr>
</table>
 




## -remarks



The <b>FltSetEcpListIntoCallbackData</b> routine provides a mechanism for passing extra create parameters down the file system filter stack to underlying minifilter and legacy filter drivers.

To retrieve an attached ECP list from a given callback-data object, use the <a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a> routine.




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="..\fltkernel\nf-fltkernel-fltdeleteextracreateparameterlookasidelist.md">FltDeleteExtraCreateParameterLookasideList</a>



<a href="..\fltkernel\nf-fltkernel-fltisecpacknowledged.md">FltIsEcpAcknowledged</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>



<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>



<a href="..\fltkernel\nf-fltkernel-fltacknowledgeecp.md">FltAcknowledgeEcp</a>



<a href="..\fltkernel\nf-fltkernel-fltisecpfromusermode.md">FltIsEcpFromUserMode</a>



<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md">FltFreeExtraCreateParameterList</a>



<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltfindextracreateparameter.md">FltFindExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltinitextracreateparameterlookasidelist.md">FltInitExtraCreateParameterLookasideList</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>



<a href="..\fltkernel\nf-fltkernel-fltgetnextextracreateparameter.md">FltGetNextExtraCreateParameter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSetEcpListIntoCallbackData routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

