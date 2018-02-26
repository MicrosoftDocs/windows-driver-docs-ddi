---
UID: NF:fwpsk.FwpsAcquireClassifyHandle0
title: FwpsAcquireClassifyHandle0 function
author: windows-driver-content
description: The FwpsAcquireClassifyHandle0 function generates a classification handle that is used to identify asynchronous classification operations and requests for writable layer data.Note  FwpsAcquireClassifyHandle0 is a specific version of FwpsAcquireClassifyHandle. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwpsacquireclassifyhandle0.htm
old-project: netvista
ms.assetid: 7348d937-6541-47a7-ae70-7d851d41bc1a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , 0, A, C, F, FwpsAcquireClassifyHandle0, FwpsAcquireClassifyHandle0 function [Network Drivers Starting with Windows Vista], H, a, c, d, e, f, fwpsk/FwpsAcquireClassifyHandle0, i, l, n, netvista.fwpsacquireclassifyhandle0, p, q, r, s, u, w, wfp_ref_2_funct_3_fwps_A-B_c0b568dd-f546-4bab-a012-14f4d2a8d846.xml, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	fwpkclnt.lib
-	fwpkclnt.dll
apiname:
-	FwpsAcquireClassifyHandle0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsAcquireClassifyHandle0 function


## -description


The 
  <b>FwpsAcquireClassifyHandle0</b> function generates a classification handle that is used to identify
  asynchronous classification operations and requests for writable layer data.
<div class="alert"><b>Note</b>  <b>FwpsAcquireClassifyHandle0</b> is a specific version of <b>FwpsAcquireClassifyHandle</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS NTAPI FwpsAcquireClassifyHandle0(
  _In_  void   *classifyContext,
  _In_  UINT32 flags,
  _Out_ UINT64 *classifyHandle
);
````


## -parameters




### -param classifyContext [in]

The 
     <i>classifyContext</i> parameter from 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn1.md">classifyFn1</a>. The WFP engine passes this
     value to the callout driver's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a>.


### -param flags [in]

Reserved for future use. Set to 0.


### -param classifyHandle [out]

A pointer to a variable that receives a classification handle. This handle is needed by subsequent
     function calls as noted in Remarks.


## -returns



The 
     <b>FwpsAcquireClassifyHandle0</b> function returns one of the following NTSTATUS codes.

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
A handle to the classify request was successfully returned. The variable that the 
       <i>classifyHandle</i> parameter points to contains the handle for the classify request.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>
 




## -remarks



<b>FwpsAcquireClassifyHandle0</b> is a support function for asynchronous classification and data
    modification. The handle returned by this function is required as a parameter for the following
    functions:

<ul>
<li>

<a href="..\fwpsk\nf-fwpsk-fwpspendclassify0.md">FwpsPendClassify0</a>


</li>
<li>

<a href="..\fwpsk\nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md">
       FwpsAcquireWritableLayerDataPointer0</a>


</li>
<li>

<a href="..\fwpsk\nf-fwpsk-fwpsapplymodifiedlayerdata0.md">
       FwpsApplyModifiedLayerData0</a>


</li>
<li>

<a href="..\fwpsk\nf-fwpsk-fwpscompleteclassify0.md">FwpsCompleteClassify0</a>


</li>
<li>

<a href="..\fwpsk\nf-fwpsk-fwpsreleaseclassifyhandle0.md">FwpsReleaseClassifyHandle0</a>


</li>
</ul>
For each call to this function, the callout driver must call 
    <a href="..\fwpsk\nf-fwpsk-fwpsreleaseclassifyhandle0.md">FwpsReleaseClassifyHandle0</a> to
    free the system resources associated with the handle.




## -see-also

<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn1.md">classifyFn1</a>



<a href="..\fwpsk\nf-fwpsk-fwpspendclassify0.md">FwpsPendClassify0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a>



<a href="..\fwpsk\nf-fwpsk-fwpscompleteclassify0.md">FwpsCompleteClassify0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsreleaseclassifyhandle0.md">FwpsReleaseClassifyHandle0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsAcquireClassifyHandle0 function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

