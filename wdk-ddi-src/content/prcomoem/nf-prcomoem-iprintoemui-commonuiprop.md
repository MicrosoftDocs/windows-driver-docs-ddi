---
UID: NF:prcomoem.IPrintOemUI.CommonUIProp
title: IPrintOemUI::CommonUIProp method
author: windows-driver-content
description: The IPrintOemUI::CommonUIProp method allows a user interface plug-in to modify an existing printer property sheet page.
old-location: print\iprintoemui_commonuiprop.htm
old-project: print
ms.assetid: 6218913c-d11c-4646-a292-5f8740097d58
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemUI, IPrintOemUI::CommonUIProp, CommonUIProp
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
req.alt-api: IPrintOemUI.CommonUIProp
req.alt-loc: prcomoem.h
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUI::CommonUIProp method



## -description
The <code>IPrintOemUI::CommonUIProp</code> method allows a user interface plug-in to modify an existing printer property sheet page.



## -syntax

````
HRESULT CommonUIProp(
   DWORD         dwMode,
   POEMCUIPPARAM pOemCUIPParam
);
````


## -parameters

### -param dwMode 

Caller-supplied integer constant indicating which property sheet page should be modified. The following constants are valid.

<table>
<tr>
<th>Value</th>
<th>Definition</th>
</tr>
<tr>
<td>
OEMCUIP_DOCPROP

</td>
<td>
The method is being called to modify the Layout, Paper/Quality, or Advanced page of the document property sheet.

</td>
</tr>
<tr>
<td>
OEMCUIP_PRNPROP

</td>
<td>
The method is being called to modify the Device Settings page of the printer property sheet.

</td>
</tr>
</table>
 


### -param pOemCUIPParam 

Caller-supplied pointer to an <a href="..\printoem\ns-printoem-_oemcuipparam.md">OEMCUIPPARAM</a> structure.


## -returns
The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not implemented.

 


## -remarks
When a user interface plug-in's <code>IPrintOemUI::CommonUIProp</code> method is called, it should return customized property sheet option items in order to modify an existing printer property sheet page.

The <code>IPrintOemUI::CommonUIProp</code> method is called by the printer driver's <a href="https://msdn.microsoft.com/2a8cf38f-8e27-4e08-9c0f-5d1a4cd854ac">printer interface DLL</a>. The method should supply an array of <a href="..\compstui\ns-compstui-_optitem.md">OPTITEM</a> structures describing property sheet items, along with a callback function for processing user modifications to option values.

You should expect the method to be called twice for each property sheet. The method's <i>dwMode</i> parameter value indicates whether it is being called to make changes to the printer property sheet or the document property sheet.

The first time it is called, the method should just return the number of <a href="..\compstui\ns-compstui-_optitem.md">OPTITEM</a> structures to be added. This number should be placed in the <a href="..\printoem\ns-printoem-_oemcuipparam.md">OEMCUIPPARAM</a> structure's <b>cOEMOptItems</b> member. The printer interface DLL then allocates enough memory to store the specified number of OPTITEMs, and calls <code>IPrintOemUI::CommonUIProp</code> again.

The second time it is called, the <code>IPrintOemUI::CommonUIProp</code> method should do the following:

Fill the driver-supplied array of OPTITEM structures with option descriptions. This array is pointed to by the OEMCUIPPARAM structure's <b>pOEMOptItems</b> member, and the number of allocated array elements is contained in the structure's <b>cOEMOptItems</b> member. (For information about specifying OPTITEM member values, see the description of the OEMCUIPPARAM structure's <b>pOEMOptItems</b> member).

Return the number of structures added to the OPTITEM array by placing the number in the OEMCUIPPARAM structure's <b>cOEMOptItems</b> member.

Return the address of a callback function in the OEMCUIPPARAM structure's <b>OEMCUIPCallback</b> member. This callback function is called when a user modifies the property sheet page. The callback function must be of type <a href="..\printoem\nc-printoem-oemcuipcallback.md">OEMCUIPCALLBACK</a>.

Optionally, return the address of a private data structure by placing it in the OEMCUIPPARAM structure's <b>pOEMUserData</b> member. The callback function specified by the structure's <b>OEMCUIPCallback</b> member receives the OEMCUIPPARAM structure's address as an input parameter and can therefore obtain the private data's address.

Space for the private data structure should be allocated by calling the Microsoft Windows SDK <b>HeapAlloc</b> function, using the handle contained in the OEMCUIPPARAM structure's <b>hOEMHeap</b> member.

If <code>IPrintOemUI::CommonUIProp</code> methods are exported by multiple user interface plug-ins, the methods are called in the order that the plug-ins are specified for installation.

For more information, see <a href="https://msdn.microsoft.com/98338017-96a0-414c-9b80-bcb98eff61e5">Modifying a Driver-Supplied Property Sheet Page</a>.</p>