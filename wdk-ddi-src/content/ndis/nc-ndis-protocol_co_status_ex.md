---
UID: NC:ndis.PROTOCOL_CO_STATUS_EX
title: PROTOCOL_CO_STATUS_EX
author: windows-driver-content
description: The ProtocolCoStatusEx function indicates status changes from underlying connection-oriented drivers or from NDIS.Note  You must declare the function by using the PROTOCOL_CO_STATUS_EX type.
old-location: netvista\protocolcostatusex.htm
old-project: netvista
ms.assetid: 1416ad56-548c-4f12-9922-9ab9a7e4fd3a
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: PROTOCOL_CO_STATUS_EX, ProtocolCoStatusEx, ProtocolCoStatusEx callback function [Network Drivers Starting with Windows Vista], condis_status_ref_683f5893-6979-4335-966b-41d48bd0fda3.xml, ndis/ProtocolCoStatusEx, netvista.protocolcostatusex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	ProtocolCoStatusEx
product:
- Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CO_STATUS_EX callback


## -description


The 
  <i>ProtocolCoStatusEx</i> function indicates status changes from underlying connection-oriented drivers or
  from NDIS.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CO_STATUS_EX</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param ProtocolBindingContext [in]

A handle to a protocol driver-allocated context area. The protocol driver maintains the
     per-binding context information in this context area. The driver supplied this handle to NDIS when the
     driver called the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function.


### -param ProtocolVcContext [in]

A handle to a protocol driver-allocated context area in which the protocol driver maintains
     virtual connection (VC) run-time state information. If the status indication is 
     <u>not</u> VC-specific, this parameter is <b>NULL</b>. Otherwise, the protocol driver originally supplied this
     handle either when it called the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a> function or from its 
     <a href="https://msdn.microsoft.com/b086dd24-74f5-474a-8684-09bf92ac731b">ProtocolCoCreateVc</a> function.


### -param StatusIndication [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567373">NDIS_STATUS_INDICATION</a> structure
     that contains the status information.


## -returns



None




## -remarks



NDIS calls 
    <i>ProtocolCoStatusEx</i> to notify a protocol driver about changes in the status of an underlying CoNDIS
    driver. A <b>NULL</b> VC handle for the 
    <i>ProtocolVcContext</i> parameter indicates a status change that is not specific to a VC. For a non-<b>NULL</b>
    VC handle, NDIS restricts the status notification to clients or call managers that share this VC
    handle.

NDIS serializes status indications for each protocol binding. To determine link status, use the status
    indications from underlying drivers instead of OID queries. These status indications will improve system
    performance and avoid possible race conditions.

NDIS calls 
    <i>ProtocolCoStatusEx</i> at IRQL &lt;= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCoStatusEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCoStatusEx</i> function that is named "MyCoStatusEx", use the <b>PROTOCOL_CO_STATUS_EX</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CO_STATUS_EX MyCoStatusEx;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyCoStatusEx(
    NDIS_HANDLE  ProtocolBindingContext,
    NDIS_HANDLE  ProtocolVcContext,
    PNDIS_STATUS_INDICATION  StatusIndication
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CO_STATUS_EX</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CO_STATUS_EX</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567373">NDIS_STATUS_INDICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/b086dd24-74f5-474a-8684-09bf92ac731b">ProtocolCoCreateVc</a>
 

 

