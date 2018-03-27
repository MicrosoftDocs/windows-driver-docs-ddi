---
UID: NC:fwpsk.FWPS_INJECT_COMPLETE0
title: FWPS_INJECT_COMPLETE0
author: windows-driver-content
description: The filter engine calls a callout's completionFn callout function whenever packet data, described by the netBufferList parameter in one of the packet injection functions, has been injected into the network stack.
old-location: netvista\completionfn.htm
old-project: netvista
ms.assetid: c03656ec-f0fe-49f5-8a04-2d26ef23c50a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FWPS_INJECT_COMPLETE0, completionFn, completionFn callback function [Network Drivers Starting with Windows Vista], fwpsk/completionFn, netvista.completionfn, wfp_ref_2_funct_4_callout_bc142e7e-f390-4b8c-b82b-c13077e1d6bf.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Fwpsk.h
api_name:
-	completionFn
product: Windows
targetos: Windows
req.typenames: INSTANCE_PARTIAL_INFORMATION, PINSTANCE_PARTIAL_INFORMATION
---

# FWPS_INJECT_COMPLETE0 callback


## -description


The filter engine calls a callout's 
  <i>completionFn</i> callout function whenever packet data, described by the 
  <i>netBufferList</i> parameter in one of the 
  <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">packet injection functions</a>, has been
  injected into the network stack.


## -parameters




### -param *context [in]

A pointer to the 
     <i>completionContext</i> parameter of one of the 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">packet injection functions</a> called
     by the callout driver.


### -param *netBufferList [in, out]

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

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef void (NTAPI *FWPS_INJECT_COMPLETE0) completionFn</pre>
</td>
</tr>
</table></span></div>
The 
    <b>Status</b> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure pointed to by 
    <i>NetBufferList</i> indicates the result of the injection operation.

After packet data in a cloned or created <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure chain has successfully been
    injected into the network stack by one of the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">packet injection functions</a>, 
    <i>completionFn</i> is called.

If the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551213">FwpsStreamInjectAsync0</a> function is
    called to inject a chain of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures, 
    <i>completionFn</i> will be called once for each <b>NET_BUFFER_LIST</b> in the chain, each time using the same 
    <i>completionContext</i> parameter specified in 
    <b>FwpsStreamInjectAsync0</b>. In this case, the callout driver's 
    <i>completionFn</i> implementation should call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551170">FwpsFreeCloneNetBufferList0</a> to
    free the currently indicated <b>NET_BUFFER_LIST</b>.

The filter engine calls a callout's 
    <i>completionFn</i> callout function at IRQL &lt;= DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543875">Callout Driver Callout Functions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551140">FwpsCalloutRegister0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551143">FwpsCalloutRegister1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551170">FwpsFreeCloneNetBufferList0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551180">FwpsInjectionHandleCreate0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551181">FwpsInjectionHandleDestroy0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551213">FwpsStreamInjectAsync0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">Packet Injection Functions</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_INJECT_COMPLETE0 callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

