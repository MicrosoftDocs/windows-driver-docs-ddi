---
UID: NS:fwpsk._FWPS_CONNECT_REQUEST0
title: "_FWPS_CONNECT_REQUEST0"
author: windows-driver-content
description: The FWPS_CONNECT_REQUEST0 structure defines modifiable data for the FWPM_LAYER_ALE_AUTH_CONNECT_REDIRECT_V4 and FWPM_LAYER_ALE_AUTH_CONNECT_REDIRECT_V6 layers.
old-location: netvista\fwps_connect_request0.htm
old-project: netvista
ms.assetid: dee5586d-62fd-4e08-854c-c7d44be60a71
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FWPS_CONNECT_REQUEST0, FWPS_CONNECT_REQUEST0 structure [Network Drivers Starting with Windows Vista], _FWPS_CONNECT_REQUEST0, fwpsk/FWPS_CONNECT_REQUEST0, netvista.fwps_connect_request0, wfp_ref_3_struct_3_fwps_A-E_af2ba16d-4454-4f69-9682-c9f759ef26e8.xml
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fwpsk.h
apiname:
-	FWPS_CONNECT_REQUEST0
product: Windows
targetos: Windows
req.typenames: FWPS_CONNECT_REQUEST0
---

# _FWPS_CONNECT_REQUEST0 structure


## -description


The <b>FWPS_CONNECT_REQUEST0</b> structure defines modifiable data for the
  <b>FWPM_LAYER_ALE_AUTH_CONNECT_REDIRECT_V4</b> and <b>FWPM_LAYER_ALE_AUTH_CONNECT_REDIRECT_V6</b> layers. The callout
  driver uses this data to inspect or modify the connection information.
<div class="alert"><b>Note</b>  <b>FWPS_CONNECT_REQUEST0</b> is a specific version of <b>FWPS_CONNECT_REQUEST</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
typedef struct _FWPS_CONNECT_REQUEST0 {
  SOCKADDR_STORAGE              localAddressAndPort;
  SOCKADDR_STORAGE              remoteAddressAndPort;
  UINT64                        portReservationToken;
  DWORD                         localRedirectTargetPID;
  struct _FWPS_CONNECT_REQUEST0  *previousVersion;
  UINT64                        modifierFilterId;
#if (NTDDI_VERSION >= NTDDI_WIN8)
  HANDLE                         localRedirectHandle;
  void                          * localRedirectContext;
  SIZE_T                         localRedirectContextSize;
#endif 
} FWPS_CONNECT_REQUEST0;
````


## -struct-fields




### -field localAddressAndPort

The local transport address of the connect request. This is an IPV4 or IPV6 address and TCP port
     formatted as a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff570825">SOCKADDR_STORAGE</a> structure.


### -field remoteAddressAndPort

The remote transport address of the connect request. This is an IPV4 or IPV6 address and TCP/UDP
     port formatted as a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff570825">SOCKADDR_STORAGE</a> structure.


### -field portReservationToken

A token used to reserve the appropriate port. The token is obtained when a port is reserved by
     calling either 
     <a href="https://msdn.microsoft.com/19DAF828-B0E4-49E2-843D-7350C8083C45">CreatePersistentTcpPortReservation</a> or 
     <a href="https://msdn.microsoft.com/AFD2EFD1-55AF-49C9-8109-D4D1B7BB7C94">CreatePersistentUdpPortReservation</a>.


### -field localRedirectTargetPID

The process identifier of the local host process that will be handling traffic to the address
     specified in 
     <b>localAddressAndPort</b>. This value must be set for loopback redirect changes to be accepted by the
     engine.


### -field previousVersion

The previous version of the connect request data. This read-only field records the modification history of the connect request. If the connect
     request data has not been previously modified by another WFP filter, 
     <i>previousVersion</i> will be set to <b>NULL</b>.


### -field _FWPS_CONNECT_REQUEST0

 


### -field modifierFilterId

The value of the 
     <b>FilterId</b> member of the 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> function's 
     <i>filter</i> parameter. For more information about the 
     <b>FilterId</b> member, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552389">FWPS_FILTER1</a>.


### -field localRedirectHandle

 The    redirect handle that the callout driver created by calling the <a href="..\fwpsk\nf-fwpsk-fwpsredirecthandlecreate0.md">FwpsRedirectHandleCreate0</a> function.

<div class="alert"><b>Note</b>  Starting with Windows 8, the <b>localRedirectHandle</b> must be populated for redirection to work.</div>
<div> </div>

### -field localRedirectContext

A callout driver context area that the callout driver allocated by calling the 
    <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a> function.

<div class="alert"><b>Note</b>  Starting with Windows 8,  memory allocated for <b>localRedirectContext</b> will have its ownership taken by WFP, and will be freed when the proxied flow is removed.</div>
<div> </div>

### -field localRedirectContextSize

The    size, in bytes, of the callout-supplied context area.

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

## -remarks



The callout driver obtains this structure by calling the 
    <a href="..\fwpsk\nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md">
    FwpsAcquireWritableLayerDataPointer0</a> function, which returns a pointer to a <b>FWPS_CONNECT_REQUEST0</b>
    structure through the 
    <i>writableLayerData</i> parameter. The 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> function can modify the connect
    request's parameters, such as redirecting the local or remote transport address or port to another
    address or port. If it modifies the connect request's parameters, the <i>classifyFn</i> function must do the
    following:

<ul>
<li>
Make all changes to the <b>FWPS_CONNECT_REQUEST0</b> structure that was returned by 
      <a href="..\fwpsk\nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md">FwpsAcquireWritableLayerDataPointer0</a>. Only the 
      <b>remoteAddressAndPort</b>, 
      <b>portReservationToken</b>, <b>localRedirectTargetPID</b>, <b>localRedirectHandle</b>, <b>localRedirectContext</b>, and <b>localRedirectContextSize</b>  members can be modified.

</li>
<li>
Call 
      <a href="..\fwpsk\nf-fwpsk-fwpsapplymodifiedlayerdata0.md">
      FwpsApplyModifiedLayerData0</a> with the 
      <i>modifiedLayerData</i> parameter set to the address of the <b>FWPS_CONNECT_REQUEST0</b> structure, even if the callout driver didn't modify any data. This value
      must be the same as the 
      <i>modifiedLayerData</i> parameter value returned through 
      <a href="..\fwpsk\nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md">
      FwpsAcquireWritableLayerDataPointer0</a>.

</li>
</ul>
This structure acts as a linked list that contains a record of all the changes made by other callout
    drivers. There is previous version information if the 
    <b>previousVersion</b> member is not <b>NULL</b>. To examine the complete version history, the callout driver
    must continue to examine the 
    <b>previousVersion</b> member of each structure in the list until it is set to <b>NULL</b>.




## -see-also

<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>



<a href="..\fwpsk\nf-fwpsk-fwpsredirecthandlecreate0.md">FwpsRedirectHandleCreate0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md">
   FwpsAcquireWritableLayerDataPointer0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552389">FWPS_FILTER1</a>



<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-bind-or-connect-redirection">Using Bind or Connect
   Redirection</a>



<a href="..\fwpsk\nf-fwpsk-fwpsapplymodifiedlayerdata0.md">FwpsApplyModifiedLayerData0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570825">SOCKADDR_STORAGE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_CONNECT_REQUEST0 structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

