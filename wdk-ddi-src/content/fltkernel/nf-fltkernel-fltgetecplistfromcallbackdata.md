---
UID: NF:fltkernel.FltGetEcpListFromCallbackData
title: FltGetEcpListFromCallbackData function
author: windows-driver-content
description: The FltGetEcpListFromCallbackData routine returns a pointer to an extra create parameter context structure (ECP) list that is associated with a given create operation callback-data object.
old-location: ifsk\fltgetecplistfromcallbackdata.htm
old-project: ifsk
ms.assetid: 4e172b98-81f8-4e20-a622-232378114cf3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltApiRef_e_to_o_781f52ec-4262-4205-81bb-2a0e824f50af.xml, fltkernel/FltGetEcpListFromCallbackData, ifsk.fltgetecplistfromcallbackdata, FltGetEcpListFromCallbackData, FltGetEcpListFromCallbackData routine [Installable File System Drivers]
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
-	FltGetEcpListFromCallbackData
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetEcpListFromCallbackData function


## -description


The <b>FltGetEcpListFromCallbackData </b>routine returns a pointer to an extra create parameter context structure (ECP) list that is associated with a given create operation callback-data object.


## -syntax


````
NTSTATUS FltGetEcpListFromCallbackData(
  _In_  PFLT_FILTER        Filter,
  _In_  PFLT_CALLBACK_DATA Data,
  _Out_ PECP_LIST          *EcpList
);
````


## -parameters




### -param Filter [in]

An opaque filter pointer to the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param CallbackData

TBD


### -param EcpList [out]

Receives a pointer to the ECP list that is associated with the <i>Data</i> callback-data object.


#### - Data [in]

A pointer to a callback-data object of type <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>, which represents the create operation.


## -returns


<b>FltGetEcpListFromCallbackData </b>returns one of the following NTSTATUS values:
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
<i>EcpList</i> received a pointer to the ECP list that is associated with the given callback-data object. If the callback-data object has no associated ECP, STATUS_SUCCESS is returned and <i>EcpList </i>is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The given callback-data object was not an IRP-based create operation.  In this case, <i>EcpList</i> is undefined.

</td>
</tr>
</table> 



## -remarks


To attach an ECP list to a callback-data object, use the <a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a> routine.



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltgetnextextracreateparameter.md">FltGetNextExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltdeleteextracreateparameterlookasidelist.md">FltDeleteExtraCreateParameterLookasideList</a>

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>

<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>

<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>

<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltacknowledgeecp.md">FltAcknowledgeEcp</a>

<a href="..\fltkernel\nf-fltkernel-fltisecpfromusermode.md">FltIsEcpFromUserMode</a>

<a href="..\fltkernel\nf-fltkernel-fltisecpacknowledged.md">FltIsEcpAcknowledged</a>

<a href="..\fltkernel\nf-fltkernel-fltfindextracreateparameter.md">FltFindExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>

<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md">FltFreeExtraCreateParameterList</a>

<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a>

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltinitextracreateparameterlookasidelist.md">FltInitExtraCreateParameterLookasideList</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetEcpListFromCallbackData routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

