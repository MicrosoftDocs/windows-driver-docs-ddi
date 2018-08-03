---
UID: NS:fwpsk._FWPS_BIND_REQUEST0
title: "_FWPS_BIND_REQUEST0"
author: windows-driver-content
description: The FWPS_BIND_REQUEST0 structure defines modifiable data for the FWPM_LAYER_ALE_AUTH_BIND_REDIRECT_V4 and FWPM_LAYER_ALE_AUTH_BIND_REDIRECT_V6 layers.
old-location: netvista\fwps_bind_request0.htm
tech.root: netvista
ms.assetid: 1a311470-b443-41d8-866f-10bf3120c13c
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: FWPS_BIND_REQUEST0, FWPS_BIND_REQUEST0 structure [Network Drivers Starting with Windows Vista], _FWPS_BIND_REQUEST0, fwpsk/FWPS_BIND_REQUEST0, netvista.fwps_bind_request0, wfp_ref_3_struct_3_fwps_A-E_2be0409e-0b99-44ba-ad3c-bc3c6bb1bee7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fwpsk.h
api_name:
-	FWPS_BIND_REQUEST0
product:
- Windows
targetos: Windows
req.typenames: FWPS_BIND_REQUEST0
---

# _FWPS_BIND_REQUEST0 structure


## -description


The <b>FWPS_BIND_REQUEST0</b> structure defines modifiable data for the FWPM_LAYER_ALE_AUTH_BIND_REDIRECT_V4
  and FWPM_LAYER_ALE_AUTH_BIND_REDIRECT_V6 layers. The callout driver uses this data to inspect or modify the
  connection information.
<div class="alert"><b>Note</b>  <b>FWPS_BIND_REQUEST0</b> is a specific version of <b>FWPS_BIND_REQUEST</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -struct-fields




### -field localAddressAndPort

The local transport address of the bind request. This is an IPV4 or IPV6 address and TCP/UDP port
     formatted as a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff570825">SOCKADDR_STORAGE</a> structure.


### -field portReservationToken

A token used to reserve the appropriate port. The token is obtained when a port is reserved by
     calling either 
     <a href="https://msdn.microsoft.com/19DAF828-B0E4-49E2-843D-7350C8083C45">CreatePersistentTcpPortReservation</a> or 
     <a href="https://msdn.microsoft.com/AFD2EFD1-55AF-49C9-8109-D4D1B7BB7C94">CreatePersistentUdpPortReservation</a>. Both reservation functions can be found in iphlpapi.h.


### -field previousVersion

The previous version of the bind request data. This read-only field records the modification history of the bind request. This member is preinitialized with a pointer to a singly linked list with the index set to the record for the current FWPS_BIND_REQUEST0 data.



### -field modifierFilterId

The value of the 
     <b>FilterId</b> member of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> function's 
     <i>filter</i> parameter. For more information about the 
     <b>FilterId</b> member, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552389">FWPS_FILTER1</a>.


## -remarks



The callout driver obtains this structure by calling the 
    <a href="https://msdn.microsoft.com/79816d01-bf27-49d0-b6f1-083b7e87cc4e">
    FwpsAcquireWritableLayerDataPointer0</a> function, which returns a pointer to a <b>FWPS_BIND_REQUEST0</b>
    structure through the 
    <i>writableLayerData</i> parameter.

The 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> function can modify the bind
    request's parameters, such as redirecting the local transport address or port to another address or port. If
    it modifies the bind request's parameters, the  
    <i>classifyFn</i> function must do the following:

<ul>
<li>
Make all changes to the <b>FWPS_BIND_REQUEST0</b> structure that was returned by
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff550087">FwpsAcquireWritableLayerDataPointer0</a>. Only the 
      <b>localAddressAndPort</b> and 
      <b>portReservationToken</b> members can be modified.

</li>
<li>
Call 
      <a href="https://msdn.microsoft.com/d32c19b6-462e-48e3-b22b-02542dca9cc4">
      FwpsApplyModifiedLayerData0</a> with the 
      <i>modifiedLayerData</i> parameter set to the address of the <b>FWPS_BIND_REQUEST0</b> structure, even if the callout driver didn't modify any data. This value
      must be the same as the 
      <i>modifiedLayerData</i> parameter value that was returned by 
      <a href="https://msdn.microsoft.com/79816d01-bf27-49d0-b6f1-083b7e87cc4e">
      FwpsAcquireWritableLayerDataPointer0</a>.

</li>
</ul>
This structure acts as a linked list that contains a record of all changes made by other callout
    drivers. There is previous version information if the 
    <b>previousVersion</b> member is not <b>NULL</b>. To examine the complete version history, the callout driver
    must continue to examine the 
    <b>previousVersion</b> member of each structure in the list until it is finds a node that has this member set to a value of <b>NULL</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552389">FWPS_FILTER1</a>



<a href="https://msdn.microsoft.com/79816d01-bf27-49d0-b6f1-083b7e87cc4e">
   FwpsAcquireWritableLayerDataPointer0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551137">FwpsApplyModifiedLayerData0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570825">SOCKADDR_STORAGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a>
 

 

