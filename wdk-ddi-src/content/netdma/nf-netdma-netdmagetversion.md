---
UID: NF:netdma.NetDmaGetVersion
title: NetDmaGetVersion function
author: windows-driver-content
description: Note  The NetDMA interface is not supported in Windows 8 and later. The NetDmaGetVersion function returns the version of the NetDMA interface that the local computer supports.
old-location: netvista\netdmagetversion.htm
old-project: netvista
ms.assetid: eec8ba30-0f9e-4487-ba0d-99587d97b44a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NetDmaGetVersion function [Network Drivers Starting with Windows Vista], NetDmaGetVersion, netdma_ref_bb1adf18-d43d-4dc2-b780-1a1322014581.xml, netdma/NetDmaGetVersion, netvista.netdmagetversion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NetDMA 2.0 and NetDMA 1.1 drivers in Windows Server 2008.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	netdma.h
apiname: 
-	NetDmaGetVersion
product: Windows
targetos: Windows
req.typenames: NET_DMA_PNP_NOTIFICATION_CODE, *PNET_DMA_PNP_NOTIFICATION_CODE
---

# NetDmaGetVersion function


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>

The 
  <b>NetDmaGetVersion</b> function returns the version of the NetDMA interface that the local computer
  supports.


## -syntax


````
UINT NetDmaGetVersion(void);
````


## -parameters





## -returns


<b>NetDmaGetVersion</b> returns a UINT value that contains the major and minor version numbers as
     follows:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>High 16 bits</b></dt>
</dl>
</td>
<td width="60%">
The major version number of the NetDMA interface.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Low 16 bits</b></dt>
</dl>
</td>
<td width="60%">
The minor version of NetDMA interface.

</td>
</tr>
</table> 



## -remarks


NetDMA provider drivers can call the 
    <b>NetDmaGetVersion</b> function to obtain the version of the NetDMA interface. A NetDMA provider must
    register as a NetDMA provider with a version equal to or lower than the NetDMA provider interface version
    that the local computer supports. The NetDMA provider driver specifies the major and minor version of the
    NetDMA provider in the 
    <b>MajorVersion</b> and 
    <b>MinorVersion</b> members of the 
    <mshelp:link keywords="netvista.net_dma_provider_characteristics" tabindex="0"><b>
    NET_DMA_PROVIDER_CHARACTERISTICS</b></mshelp:link> structure that it passes to the 
    <mshelp:link keywords="netvista.netdmaregisterprovider" tabindex="0"><b>
    NetDmaRegisterProvider</b></mshelp:link> function.
<div class="alert"><b>Note</b>  <b>NetDmaGetVersion</b> is not available in NetDMA version 1.0. To avoid using a function import that
    might stop the driver from loading, a NetDMA 1.1 or later provider driver must verify the presence of 
    <b>NetDmaGetVersion</b> before it calls 
    <b>NetDmaGetVersion</b>. To call 
    <b>NetDmaGetVersion</b>, first call the 
    <a href="..\ndis\nf-ndis-ndisgetroutineaddress.md">NdisGetRoutineAddress</a> function to
    get the entry point and then, if 
    <b>NetDmaGetVersion</b> is available, call 
    <b>NetDmaGetVersion</b> at the entry point that 
    <b>NdisGetRoutineAddress</b> provided. If the provider driver cannot get the address of 
    <b>NetDmaGetVersion</b>, the supported NetDMA interface must be version 1.0.</div><div> </div>NetDMA provider drivers call 
    <b>NetDmaGetVersion</b> at IRQL = PASSIVE_LEVEL.



## -see-also

<mshelp:link keywords="netvista.net_dma_provider_characteristics" tabindex="0"><b>
   NET_DMA_PROVIDER_CHARACTERISTICS</b></mshelp:link>

<a href="..\netdma\nf-netdma-netdmaregisterprovider.md">NetDmaRegisterProvider</a>

<a href="..\ndis\nf-ndis-ndisgetroutineaddress.md">NdisGetRoutineAddress</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NetDmaGetVersion function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

