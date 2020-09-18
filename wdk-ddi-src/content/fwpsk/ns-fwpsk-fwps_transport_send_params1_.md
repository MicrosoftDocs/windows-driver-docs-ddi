---
UID: NS:fwpsk.FWPS_TRANSPORT_SEND_PARAMS1_
title: FWPS_TRANSPORT_SEND_PARAMS1_ (fwpsk.h)
description: The FWPS_TRANSPORT_SEND_PARAMS1 structure defines properties of an outbound transport layer packet.Note  FWPS_TRANSPORT_SEND_PARAMS1 is the specific version of FWPS_TRANSPORT_SEND_PARAMS used in Windows 7 and later.
old-location: netvista\fwps_transport_send_params1.htm
tech.root: netvista
ms.assetid: 8d5653e4-a755-4066-b25a-f8f589821412
ms.date: 05/02/2018
keywords: ["FWPS_TRANSPORT_SEND_PARAMS1_ structure"]
ms.keywords: FWPS_TRANSPORT_SEND_PARAMS1, FWPS_TRANSPORT_SEND_PARAMS1 structure [Network Drivers Starting with Windows Vista], FWPS_TRANSPORT_SEND_PARAMS1_, fwpsk/FWPS_TRANSPORT_SEND_PARAMS1, netvista.fwps_transport_send_params1, wfp_ref_3_struct_3_fwps_P-Z_55024e38-5ae1-4a2c-8595-2722e481a947.xml
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
targetos: Windows
req.typenames: FWPS_TRANSPORT_SEND_PARAMS1
f1_keywords:
 - FWPS_TRANSPORT_SEND_PARAMS1_
 - fwpsk/FWPS_TRANSPORT_SEND_PARAMS1_
 - FWPS_TRANSPORT_SEND_PARAMS1
 - fwpsk/FWPS_TRANSPORT_SEND_PARAMS1
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fwpsk.h
api_name:
 - FWPS_TRANSPORT_SEND_PARAMS1
---

# FWPS_TRANSPORT_SEND_PARAMS1_ structure


## -description

The <b>FWPS_TRANSPORT_SEND_PARAMS1</b> structure defines properties of an outbound transport layer
  packet.
<div class="alert"><b>Note</b>  <b>FWPS_TRANSPORT_SEND_PARAMS1</b> is the specific version of <b>FWPS_TRANSPORT_SEND_PARAMS</b> used in Windows 7 and later. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows Vista, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_transport_send_params0_">FWPS_TRANSPORT_SEND_PARAMS0</a> is available.</div><div> </div>

## -struct-fields

### -field remoteAddress

A pointer to a buffer that specifies the remote IP address to which the socket needs to be sent.
     The remote address specified by this member can be different than the one passed as one of the incoming
     data values to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> callout function.
     

The buffer can contain an IPv4 address (4 bytes) or an IPv6 address (16 bytes), and the address must
     be specified in network byte order. The IP version must match the 
     <i>AddressFamily</i> parameter specified in the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjecttransportsendasync1">
     FwpsInjectTransportSendAsync1</a> function.

The buffer must remain valid until the injection completion function is called.

### -field remoteScopeId

A <b>SCOPE_ID</b> structure that contains the scope identifier for the remote IP address. The scope
     identifier is provided to a callout through the 
     <b>remoteScopeId</b> member of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">
     FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> callout function. The <b>SCOPE_ID</b>
     structure is defined in 
     Ws2ipdef.h as follows.


```
typedef struct {
  union {
    struct {
      ULONG  Zone : 28;
      ULONG  Level : 4;
    };
    ULONG  Value;
  };
} SCOPE_ID, *PSCOPE_ID;
```


### -field OPTIONAL

 




#### - controlData

An optional pointer to a buffer that contains socket control data specified by the 
      <a href="https://docs.microsoft.com/windows/win32/api/winsock2/nf-winsock2-wsasendmsg">WSASendMsg</a> function. For information about the <b>WSACMSGHDR</b> type, see 
      <a href="https://docs.microsoft.com/windows/win32/api/ws2def/ns-ws2def-_wsacmsghdr">CMSGHDR</a>.

If present, socket control data is provided to a callout with the 
      <b>controlData</b> member of the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">
      FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the callout driver's 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> callout function.

If socket control data is not <b>NULL</b>, it must be deep-copied in the callout driver's implementation
      of the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> function, and the 
      <b>controlData</b> buffer must be kept valid until the injection completion
      function is called.


#### - controlDataLength

The length, in bytes, of the 
     <b>controlData</b> member.


#### - headerIncludeHeader

The transport header to include.


#### - headerIncludeHeaderLength

The length, in bytes, of the 
     <b>headerIncludeHeader</b> member.

## -see-also

<a href="https://docs.microsoft.com/windows/win32/api/ws2def/ns-ws2def-_wsacmsghdr">CMSGHDR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">
   FWPS_INCOMING_METADATA_VALUES0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjecttransportsendasync1">
   FwpsInjectTransportSendAsync1</a>



<a href="https://docs.microsoft.com/windows/win32/api/winsock2/nf-winsock2-wsasendmsg">WSASendMsg</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>

