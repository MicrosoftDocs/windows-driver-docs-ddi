---
UID: NC:ndis.PROTOCOL_CO_STATUS_EX
title: PROTOCOL_CO_STATUS_EX (ndis.h)
description: The ProtocolCoStatusEx function indicates status changes from underlying connection-oriented drivers or from NDIS.Note  You must declare the function by using the PROTOCOL_CO_STATUS_EX type.
old-location: netvista\protocolcostatusex.htm
tech.root: netvista
ms.assetid: 1416ad56-548c-4f12-9922-9ab9a7e4fd3a
ms.date: 05/02/2018
keywords: ["PROTOCOL_CO_STATUS_EX callback function"]
ms.keywords: PROTOCOL_CO_STATUS_EX, PROTOCOL_CO_STATUS_EX callback, ProtocolCoStatusEx, ProtocolCoStatusEx callback function [Network Drivers Starting with Windows Vista], condis_status_ref_683f5893-6979-4335-966b-41d48bd0fda3.xml, ndis/ProtocolCoStatusEx, netvista.protocolcostatusex
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - PROTOCOL_CO_STATUS_EX
 - ndis/PROTOCOL_CO_STATUS_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - ProtocolCoStatusEx
---

# PROTOCOL_CO_STATUS_EX callback function


## -description

The 
  <i>ProtocolCoStatusEx</i> function indicates status changes from underlying connection-oriented drivers or
  from NDIS.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CO_STATUS_EX</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters

### -param ProtocolBindingContext 

[in]
A handle to a protocol driver-allocated context area. The protocol driver maintains the
     per-binding context information in this context area. The driver supplied this handle to NDIS when the
     driver called the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function.

### -param ProtocolVcContext 

[in]
A handle to a protocol driver-allocated context area in which the protocol driver maintains
     virtual connection (VC) run-time state information. If the status indication is 
     <u>not</u> VC-specific, this parameter is <b>NULL</b>. Otherwise, the protocol driver originally supplied this
     handle either when it called the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a> function or from its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.

### -param StatusIndication 

[in]
A pointer to an 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_status_indication">NDIS_STATUS_INDICATION</a> structure
     that contains the status information.

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
    <i>ProtocolCoStatusEx</i> at IRQL <= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCoStatusEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCoStatusEx</i> function that is named "MyCoStatusEx", use the <b>PROTOCOL_CO_STATUS_EX</b> type as shown in this code example:


```
PROTOCOL_CO_STATUS_EX MyCoStatusEx;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyCoStatusEx(
    NDIS_HANDLE  ProtocolBindingContext,
    NDIS_HANDLE  ProtocolVcContext,
    PNDIS_STATUS_INDICATION  StatusIndication
    )
  {...}
```

The <b>PROTOCOL_CO_STATUS_EX</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CO_STATUS_EX</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_status_indication">NDIS_STATUS_INDICATION</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a>