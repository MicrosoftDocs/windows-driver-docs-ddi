---
UID: NF:prcomoem.IPrintOemPS.PublishDriverInterface
title: IPrintOemPS::PublishDriverInterface (prcomoem.h)
description: The IPrintOemPS::PublishDriverInterface method allows a rendering plug-in for Pscript5 to obtain the Pscript5 driver's IPrintCorePS2, IPrintOemDriverPS, or IPrintCoreHelperPS interface.
old-location: print\iprintoemps_publishdriverinterface.htm
tech.root: print
ms.assetid: f878a674-7c08-4a7a-ab00-6c79f02566be
ms.date: 04/20/2018
keywords: ["IPrintOemPS::PublishDriverInterface"]
ms.keywords: IPrintOemPS interface [Print Devices],PublishDriverInterface method, IPrintOemPS.PublishDriverInterface, IPrintOemPS::PublishDriverInterface, PublishDriverInterface, PublishDriverInterface method [Print Devices], PublishDriverInterface method [Print Devices],IPrintOemPS interface, prcomoem/IPrintOemPS::PublishDriverInterface, print.iprintoemps_publishdriverinterface, print_unidrv-pscript_rendering_b7e2dc4b-ecc1-41bd-853d-4099614b5cae.xml
f1_keywords:
 - "prcomoem/IPrintOemPS.PublishDriverInterface"
 - "IPrintOemPS.PublishDriverInterface"
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- prcomoem.h
api_name:
- IPrintOemPS.PublishDriverInterface
targetos: Windows
req.typenames: 
---

# IPrintOemPS::PublishDriverInterface


## -description


The <code>IPrintOemPS::PublishDriverInterface</code> method allows a rendering plug-in for Pscript5 to obtain the Pscript5 driver's <b>IPrintCorePS2</b>, <b>IPrintOemDriverPS</b>, or <b>IPrintCoreHelperPS</b> interface.


## -parameters




### -param pIUnknown

Caller-supplied pointer to the <b>IUnknown</b> interface of the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/print/iprintcoreps2-com-interface">IPrintCorePS2 COM Interface</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/print/iprintoemdriverps-com-interface">IPrintOemDriverPS COM Interface</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelperps">IPrintCoreHelperPS Interface</a>.


## -returns



The method must return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed

</td>
</tr>
</table>
 




## -remarks



The Pscript5 driver supports the <b>IPrintCorePS2</b>, <b>IPrintOemDriverPS</b>, and <b>IPrintCoreHelperPS</b> interfaces. A rendering plug-in for Pscript5 must implement the <code>IPrintOemPS::PublishDriverInterface</code> method. The method should return information on its supported Pscript5 interfaces as follows:

<ol>
<li>
The Pscript5 driver first calls the <code>IPrintOemPS::PublishDriverInterface</code> method with the <i>pIUnknown</i> pointer set to the <b>IPrintCorePS2</b> instance's <b>IUnknown</b> interface. If the rendering plug-in is able to use the <b>IPrintCorePS2</b> interface, the method must return S_OK. Otherwise, the plug-in should return E_FAIL.

</li>
<li>
If the plug-in has returned E_FAIL, the Pscript5 driver calls the <code>IPrintOemPS::PublishDriverInterface</code> method again, but with the <i>pIUnknown</i> pointer set to the <b>IPrintOemDriverPS</b> instance's <b>IUnknown</b> interface. If the plug-in is able to use the <b>IPrintOemDriverPS</b> interface, the method must return S_OK. Otherwise, the plug-in should return E_FAIL.

</li>
<li>
If the plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-getinfo">IPrintOemPS::GetInfo</a> method has returned a value of OEMPUBLISH_IPRINTCOREHELPER in <i>pBuffer</i> in response to a call with <i>dwMode</i> set to OEMGI_GETREQUESTEDHELPERINTERFACES in <i>pBuffer</i>, the Pscript5 driver calls the <code>IPrintOemPS::PublishDriverInterface</code> method again, but with the <i>pIUnknown</i> pointer set to an object that implements the <b>IPrintCoreHelperPS</b> and <b>IPrintCoreHelper</b> interfaces. If the plug-in retains a pointer to the object interface, the method should return S_OK. Otherwise, the method should return E_FAIL.

</li>
</ol>
If the plug-in fails all calls to <code>IPrintOemPS::PublishDriverInterface</code>, the plug-in will not receive further calls. If the plug-in will be calling <b>IPrintCorePS2</b>, <b>IPrintOemDriverPS</b>, or <b>IPrintCoreHelperPS</b> interface methods, it must use the received <b>IUnknown</b> interface pointer to call <b>IUnknown::QueryInterface</b> (described in the Microsoft Windows SDK documentation) in order to obtain a pointer to the driver's supported version of the <b>IPrintCorePS2</b>, <b>IPrintOemDriverPS</b>, or <b>IPrintCoreHelperPS</b> interface. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/accessing-printer-driver-interfaces-from-plug-ins">Accessing Printer Driver Interfaces from Plug-Ins</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemps">IPrintOemPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-getinfo">IPrintOemPS::GetInfo</a>
 

 

