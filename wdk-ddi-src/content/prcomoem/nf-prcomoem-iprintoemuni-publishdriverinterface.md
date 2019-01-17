---
UID: NF:prcomoem.IPrintOemUni.PublishDriverInterface
title: IPrintOemUni::PublishDriverInterface
description: The IPrintOemUni::PublishDriverInterface method allows a rendering plug-in for Unidrv to obtain the Unidrv driver's IPrintOemDriverUni or IPrintCoreHelperUni interface.
old-location: print\iprintoemuni_publishdriverinterface.htm
tech.root: print
ms.assetid: 72bfa383-a7f2-4aa6-a45c-564928705e42
ms.date: 04/20/2018
ms.keywords: IPrintOemUni interface [Print Devices],PublishDriverInterface method, IPrintOemUni.PublishDriverInterface, IPrintOemUni::PublishDriverInterface, PublishDriverInterface, PublishDriverInterface method [Print Devices], PublishDriverInterface method [Print Devices],IPrintOemUni interface, prcomoem/IPrintOemUni::PublishDriverInterface, print.iprintoemuni_publishdriverinterface, print_unidrv-pscript_rendering_c9525b65-4bc0-42cb-b416-7b2034581b0e.xml
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemUni.PublishDriverInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni::PublishDriverInterface


## -description


The <code>IPrintOemUni::PublishDriverInterface</code> method allows a rendering plug-in for Unidrv to obtain the Unidrv driver's <b>IPrintOemDriverUni</b> or <b>IPrintCoreHelperUni</b> interface.


## -parameters




### -param pIUnknown

Caller-supplied pointer to the <b>IUnknown</b> interface of the driver's <a href="https://msdn.microsoft.com/84b3f43c-039a-4e9d-b596-41c08f1e0284">IPrintOemDriverUni COM Interface</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff552940">IPrintCoreHelperUni interface</a>.


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
The operation failed.

</td>
</tr>
</table>
 




## -remarks



A rendering plug-in for <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">Unidrv</a> must implement the <code>IPrintOemUni::PublishDriverInterface</code> method, and the method must return S_OK in response to at least one call. Otherwise, the driver will not call the plug-in's other <b>IPrintOemUni</b> interface methods.

The method should return information on its supported Unidrv interfaces as follows:

<ol>
<li>
The Unidrv driver first calls the <code>IPrintOemUI::PublishDriverInterface</code> method with the <i>pIUnknown</i> pointer set to the <b>IPrintOemDriverUni</b> instance's <b>IUnknown</b> interface. If the rendering plug-in will be calling <b>IPrintOemDriverUni</b> interface methods, it must use the received <b>IUnknown</b> interface pointer to call <b>IUnknown::QueryInterface </b>(described in the Microsoft Windows SDK documentation) in order to obtain a pointer to the driver's supported version of the <b>IPrintOemDriverUni</b> interface. For more information, see <a href="https://msdn.microsoft.com/8182cba5-4461-4ca0-8b01-342519609b1f">Interface Identifiers for Printer Drivers</a>.

</li>
<li>
If the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554256">IPrintOemUni::GetInfo</a> method has returned a value of OEMPUBLISH_IPRINTCOREHELPER in <i>pBuffer</i> in response to a call with <i>dwMode</i> set to OEMGI_GETREQUESTEDHELPERINTERFACES, the Unidrv driver calls the <code>IPrintOemUni::PublishDriverInterface</code> method again, but with the <i>pIUnknown</i> pointer set to an object that implements the <b>IPrintCoreHelperUni</b> and <b>IPrintCoreHelper</b> interfaces. If the plug-in retains a pointer to the object, the method should return S_OK. Otherwise, the method should return E_FAIL.

</li>
</ol>



## -see-also




<a href="https://msdn.microsoft.com/097366a0-2ded-435c-9b63-2b736b716032">IPrintOemUni</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554256">IPrintOemUni::GetInfo</a>
 

 

