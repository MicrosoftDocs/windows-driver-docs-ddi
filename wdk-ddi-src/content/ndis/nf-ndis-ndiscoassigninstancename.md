---
UID: NF:ndis.NdisCoAssignInstanceName
title: NdisCoAssignInstanceName function
author: windows-driver-content
description: NdisCoAssignInstanceName assigns an instance name to a VC and causes NDIS to register a GUID (globally unique identifier) for the assigned name with Windows Management Instrumentation (WMI).
old-location: netvista\ndiscoassigninstancename.htm
old-project: netvista
ms.assetid: 78a1808e-d244-4f23-bba1-c48a7b2e051b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NdisCoAssignInstanceName, NdisCoAssignInstanceName, condis_protocol_ref_48515a9c-790b-4122-8a29-2a35cf560af9.xml, NdisCoAssignInstanceName function [Network Drivers Starting with Windows Vista], netvista.ndiscoassigninstancename
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCoAssignInstanceName (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCoAssignInstanceName (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Connection_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisCoAssignInstanceName
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisCoAssignInstanceName function


## -description


<b>NdisCoAssignInstanceName</b> assigns an instance name to a VC and causes NDIS to register a GUID
  (globally unique identifier) for the assigned name with Windows Management Instrumentation (WMI).


## -syntax


````
NDIS_STATUS NdisCoAssignInstanceName(
  _In_      NDIS_HANDLE  NdisVcHandle,
  _In_      PNDIS_STRING BaseInstanceName,
  _Out_opt_ PNDIS_STRING VcInstanceName
);
````


## -parameters




### -param NdisVcHandle [in]

Specifies the handle to the VC being named. This handle was supplied by NDIS when the VC was
     originally created with 
     <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>, whether by the client in
     preparation for making an outgoing call or by the call manager in preparation for dispatching an
     incoming call to the client.


### -param BaseInstanceName [in]

Pointer to an NDIS_STRING type that describes a caller-supplied Unicode string that specifies the
     base name of the VC. The base name can be any localizable Unicode string that uniquely identifies the VC
     with respect to the other named VCs within the scope of the miniport driver. For Windows Vista and
     later, NDIS defines the NDIS_STRING type as a 
     <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> type.


### -param VcInstanceName [out, optional]

Pointer to a caller-allocated NDIS_STRING type in which this routine returns a Unicode string that
     specifies the NDIS-assigned instance name assigned for the VC.


## -returns



<b>NdisCoAssignInstanceName</b> can return any of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
NDIS assigned an instance name to the specified VC and registered a GUID for the instance name
       with WMI.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The attempt to assign an instance name to the VC failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
NDIS could not allocate a buffer for the instance name.

</td>
</tr>
</table>
 




## -remarks



After initiating the setup of a VC with 
    <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>, a call manager or
    connection-oriented client can name the VC with 
    <b>NdisCoAssignInstanceName</b>. Calling 
    <b>NdisCoAssignInstanceName</b>, causes NDIS to assign the VC an instance name and register the instance
    name with WMI. WMI clients can then enumerate the VC and query or set OIDs relative to the VC.

An integrated miniport call manager (MCM) driver cannot use 
    <b>NdisCoAssignInstanceName</b> to name its VCs. Instead, an MCM driver should create a custom GUID and
    OID for the VC and register the GUID-to-OID mapping with NDIS.

NDIS creates an instance name for the specified VC by appending an index to the base name pointed to
    by the caller. NDIS returns the complete instance name (base name + index) to the caller and then
    registers a GUID for the instance name with WMI. Only named VCs can be enumerated and queried by WMI
    clients. Unnamed VCs are not visible to WMI clients.

If the specified VC already has an instance name (assigned in a previous call to 
    <b>NdisCoAssignInstanceName</b>), NDIS returns NDIS_STATUS_SUCCESS and the 
    <i>original</i> instance name assigned to the VC. An instance name remains assigned to a VC until that VC
    is deleted.

The caller can associate the returned instance name with the handle for the named VC that NDIS
    previously returned to the caller from 
    <b>NdisCoCreateVc</b>. NDIS, however, will continue to use the VC handle--not the instance name--to refer
    to the VC in subsequent calls. The caller of 
    <b>NdisCoAssignInstanceName</b> might find the need to return the instance name to some other management
    entity.

The caller is responsible for freeing the buffer containing the returned instance name. After deleting
    the named VC with 
    <a href="..\ndis\nf-ndis-ndiscodeletevc.md">NdisCoDeleteVc</a>, the caller must free the
    buffer with 
    <a href="..\ndis\nf-ndis-ndisfreestring.md">NdisFreeString</a>.




## -see-also

<a href="..\ndis\nf-ndis-ndisfreestring.md">NdisFreeString</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\ndis\nf-ndis-ndiscodeletevc.md">NdisCoDeleteVC</a>



<a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a>



<a href="..\ndis\nc-ndis-miniport_co_oid_request.md">MiniportCoOidRequest</a>



<a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCoAssignInstanceName function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

