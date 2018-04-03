---
UID: NF:prcomoem.IPrintOemUI.PublishDriverInterface
title: IPrintOemUI::PublishDriverInterface method
author: windows-driver-content
description: The IPrintOemUI::PublishDriverInterface method allows a user interface plug-in to obtain the Unidrv or Pscript5 driver's IPrintOemDriverUI, IPrintCoreUI2, IPrintCoreHelperPS, or IPrintCoreHelperUni interface.
old-location: print\iprintoemui_publishdriverinterface.htm
old-project: print
ms.assetid: 4c2053ec-c6b3-4584-b689-dc887610c57e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintOemUI, IPrintOemUI interface [Print Devices], PublishDriverInterface method, IPrintOemUI::PublishDriverInterface, PublishDriverInterface method [Print Devices], PublishDriverInterface method [Print Devices], IPrintOemUI interface, PublishDriverInterface,IPrintOemUI.PublishDriverInterface, prcomoem/IPrintOemUI::PublishDriverInterface, print.iprintoemui_publishdriverinterface, print_unidrv-pscript_ui_d5f2a80f-fa9d-4433-9dc1-b1771f124a32.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IPrintOemUI.PublishDriverInterface
product:
- Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUI::PublishDriverInterface method


## -description


The <code>IPrintOemUI::PublishDriverInterface</code> method allows a user interface plug-in to obtain the Unidrv or Pscript5 driver's <b>IPrintOemDriverUI</b>, <b>IPrintCoreUI2</b>, <b>IPrintCoreHelperPS</b>, or <b>IPrintCoreHelperUni</b> interface.


## -parameters




### -param pIUnknown

Caller-supplied pointer to the <b>IUnknown</b> interface of the driver's <a href="https://msdn.microsoft.com/3c9df0ac-d823-4c27-bd34-85765f48b972">IPrintCoreUI2 COM Interface</a>, <a href="https://msdn.microsoft.com/ed11789f-750d-4f29-b5e0-ab299a1388db">IPrintOemDriverUI COM Interface</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff552906">IPrintCoreHelperPS Interface</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff552940">IPrintCoreHelperUni Interface</a>. See Remarks.


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



The Pscript5 driver supports the <b>IPrintCoreUI2</b>, <b>IPrintOemDriverUI</b>, and <b>IPrintCoreHelperPS</b> interfaces. Unidrv supports the <b>IPrintOemDriverUI</b> and <b>IPrintCoreHelperUni</b> interfaces. User interface plug-ins for both types of driver must implement the <code>IPrintOemUI::PublishDriverInterface</code> method.

The method should return information on its supported Pscript5 interfaces as follows:

<ol>
<li>
The Pscript5 driver first calls the <code>IPrintOemUI::PublishDriverInterface</code> method with the <i>pIUnknown</i> pointer set to the <b>IPrintCoreUI2</b> instance's <b>IUnknown</b> interface. If the user interface plug-in is able to use the <b>IPrintCoreUI2</b> interface, the method must return S_OK. Otherwise, the plug-in should return E_FAIL.

</li>
<li>
If the plug-in has returned E_FAIL, the Pscript5 driver calls the <code>IPrintOemUI::PublishDriverInterface</code> method again, but with the <i>pIUnknown</i> pointer set to the <b>IPrintOemDriverUI</b> instance's <b>IUnknown</b> interface. If the plug-in can use the <b>IPrintOemDriverUI</b> interface, the method must return S_OK. Otherwise, the plug-in should return E_FAIL.

</li>
<li>
If the plug-in's <b>IPrintOemUI::GetInfo</b> method has returned a value of OEMPUBLISH_IPRINTCOREHELPER in <i>pBuffer</i> in response to a call with <i>dwMode</i> set to OEMGI_GETREQUESTEDHELPERINTERFACES, the Pscript5 driver calls the <code>IPrintOemUI::PublishDriverInterface</code> method again, but with the <i>pIUnknown</i> pointer set to an object that implements the <b>IPrintCoreHelperPS</b> and <b>IPrintCoreHelper</b> interfaces. If the plug-in can use the <b>IPrintCoreHelperPS</b> or <b>IPrintCoreHelper</b> interface, the method should return S_OK. Otherwise, the method should return E_FAIL.

</li>
</ol>
The method should return information on its supported Unidrv interfaces as follows:

<ol>
<li>
The Unidrv driver first calls the <code>IPrintOemUI::PublishDriverInterface</code> method with the <i>pIUnknown</i> pointer set to the <b>IPrintOemDriverUI</b> instance's <b>IUnknown</b> interface. If the plug-in is able to use the <b>IPrintOemDriverUI</b> interface, the method must return S_OK. Otherwise, the plug-in should return E_FAIL.

</li>
<li>
If the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554178">IPrintOemUI::GetInfo</a> method has returned a value of OEMPUBLISH_IPRINTCOREHELPER in <i>pBuffer</i> in response to a call with <i>dwMode</i> set to OEMGI_GETREQUESTEDHELPERINTERFACES, the Unidrv driver calls the <code>IPrintOemUI::PublishDriverInterface</code> method again, but with the <i>pIUnknown</i> pointer set to an object that implements the <b>IPrintCoreHelperUni</b> and <b>IPrintCoreHelper</b> interfaces. If the plug-in uses the <b>IPrintCoreHelperUni</b> or <b>IPrintCoreHelper</b> interface, the method should return S_OK. Otherwise, the method should return E_FAIL.

</li>
</ol>
If the plug-in fails all calls to <code>IPrintOemUI::PublishDriverInterface</code>, the plug-in will not receive further calls. If the user interface plug-in will be calling <b>IPrintCoreUI2</b>, <b>IPrintOemDriverUI</b>, <b>IPrintCoreHelperPS</b>, or <b>IPrintCoreHelperUni</b> interface methods, it must use the received <b>IUnknown</b> interface pointer to call <b>IUnknown::QueryInterface </b>(described in the Microsoft Windows SDK documentation) in order to obtain a pointer to the driver's supported version of the <b>IPrintCoreUI2</b>, <b>IPrintOemDriverUI</b>, <b>IPrintCoreHelperPS</b>, or <b>IPrintCoreHelperUni</b> interface. For more information, see <a href="https://msdn.microsoft.com/8182cba5-4461-4ca0-8b01-342519609b1f">Interface Identifiers for Printer Drivers</a>.

During processing of each DDI function, UI plug-ins should not mix the use of methods of the pre-Windows Vista interfaces (for example, the <a href="https://msdn.microsoft.com/2a885dd5-d328-4aae-8771-613ff93b35ac">IPrintOemDriverUI</a> or <a href="https://msdn.microsoft.com/e2d2e486-d69d-4a6d-aaab-a7b8806665b4">IPrintCoreUI2</a> interface) and the new methods of the Windows Vista interfaces (for example, <a href="https://msdn.microsoft.com/e581d190-8185-45c1-80c7-ff8eb305360e">IPrintCoreHelperUni</a> or <a href="https://msdn.microsoft.com/2be594f1-1eb1-42e0-a345-ee7edf4d96dd">IPrintCoreHelperPS</a>) to read or write driver settings. For example, during the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554173">IPrintOemUI::DocumentPropertySheets</a> method, the UI plug-in should not use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553115">IPrintOemDriverUI::DrvUpdateUISetting</a> method to write settings and use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552959">IPrintCoreHelper::GetOption</a> method to read settings. For another example, during the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554182">IPrintOemUI::PrinterEvent</a> method, the UI plug-in should not use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553069">IPrintCoreUI2::GetOptions</a> method to read settings and use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552963">IPrintCoreHelper::SetOptions</a> method to write settings. Synchronization of the reading and writing of settings is not supported between these different versions of interfaces.




## -see-also




<a href="https://msdn.microsoft.com/0ef635dd-9598-4356-94fc-7e5237df9bd9">IPrintOemUI</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554178">IPrintOemUI::GetInfo</a>
 

 

