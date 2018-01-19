---
UID: NC:fwpsk.FWPS_INJECT_COMPLETE0
title: FWPS_INJECT_COMPLETE0
author: windows-driver-content
description: The filter engine calls a callout's completionFn callout function whenever packet data, described by the netBufferList parameter in one of the packet injection functions, has been injected into the network stack.
old-location: netvista\completionfn.htm
old-project: netvista
ms.assetid: c03656ec-f0fe-49f5-8a04-2d26ef23c50a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FwpmEngineOpen0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: completionFn
req.alt-loc: Fwpsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: PINSTANCE_PARTIAL_INFORMATION, INSTANCE_PARTIAL_INFORMATION
---

# FWPS_INJECT_COMPLETE0 callback



## -description
The filter engine calls a callout's 
  <i>completionFn</i> callout function whenever packet data, described by the 
  <i>netBufferList</i> parameter in one of the 
  <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">packet injection functions</a>, has been
  injected into the network stack.



## -prototype

````
FWPS_INJECT_COMPLETE0 completionFn;

void NTAPI completionFn(
  _In_    VOID            *context,
  _Inout_ NET_BUFFER_LIST *netBufferList,
  _In_    BOOLEAN         dispatchLevel
)
{ ... }
````


## -parameters

### -param context [in]

A pointer to the 
     <i>completionContext</i> parameter of one of the 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">packet injection functions</a> called
     by the callout driver.


### -param netBufferList [in, out]

The pointer passed in the 
     <i>netBufferList</i> parameter of one of the 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">packet injection functions</a> called
     by the callout driver.


### -param dispatchLevel [in]

A value that indicates the IRQL at which the 
     <i>completionFn</i> callout function is being called. If this parameter is <b>TRUE</b>, the 
     <i>completionFn</i> callout function is being called at IRQL = DISPATCH_LEVEL. If this parameter is
     <b>FALSE</b>, the 
     <i>completionFn</i> callout function is being called at an IRQL &lt; DISPATCH_LEVEL.


## -returns
None.


## -remarks
The FWPS_INJECT_COMPLETE0 type is defined as a pointer to the 
    <i>completionFn</i> function as follows:

The 
    <b>Status</b> member of the 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure pointed to by 
    <i>NetBufferList</i> indicates the result of the injection operation.

After packet data in a cloned or created <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure chain has successfully been
    injected into the network stack by one of the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">packet injection functions</a>, 
    <i>completionFn</i> is called.

If the 
    <a href="..\fwpsk\nf-fwpsk-fwpsstreaminjectasync0.md">FwpsStreamInjectAsync0</a> function is
    called to inject a chain of <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures, 
    <i>completionFn</i> will be called once for each <b>NET_BUFFER_LIST</b> in the chain, each time using the same 
    <i>completionContext</i> parameter specified in 
    <b>FwpsStreamInjectAsync0</b>. In this case, the callout driver's 
    <i>completionFn</i> implementation should call 
    <a href="..\fwpsk\nf-fwpsk-fwpsfreeclonenetbufferlist0.md">FwpsFreeCloneNetBufferList0</a> to
    free the currently indicated <b>NET_BUFFER_LIST</b>.

The filter engine calls a callout's 
    <i>completionFn</i> callout function at IRQL &lt;= DISPATCH_LEVEL.


## -see-also
<dl>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister0.md">FwpsCalloutRegister0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister1.md">FwpsCalloutRegister1</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsfreeclonenetbufferlist0.md">FwpsFreeCloneNetBufferList0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">FwpsInjectionHandleCreate0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandledestroy0.md">FwpsInjectionHandleDestroy0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsstreaminjectasync0.md">FwpsStreamInjectAsync0</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543875">Callout Driver Callout Functions</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">Packet Injection Functions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_INJECT_COMPLETE0 callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

