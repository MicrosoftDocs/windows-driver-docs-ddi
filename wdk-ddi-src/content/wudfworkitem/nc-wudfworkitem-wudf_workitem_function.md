---
UID: NC:wudfworkitem.WUDF_WORKITEM_FUNCTION
title: WUDF_WORKITEM_FUNCTION
author: windows-driver-content
description: A driver's OnWorkItem event callback function performs the work that is associated with a specified work item.
old-location: wdf\onworkitem.htm
old-project: wdf
ms.assetid: 4CCA1F5E-C92E-4D8D-A8C0-B8E9A0F29703
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OnWorkItem, OnWorkItem callback function, PFN_WUDF_WORKITEM, PFN_WUDF_WORKITEM callback function pointer, WUDF_WORKITEM_FUNCTION, umdf.onworkitem, wdf.onworkitem, wudfworkitem/OnWorkItem, wudfworkitem/PFN_WUDF_WORKITEM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wudfworkitem.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
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
-	UserDefined
api_location:
-	Wudfworkitem.h
api_name:
-	WUDF_WORKITEM_FUNCTION
product: Windows
targetos: Windows
req.typenames: UNICODE_STRING
req.product: Windows 10 or later.
---

# WUDF_WORKITEM_FUNCTION callback


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <i>OnWorkItem</i> event callback function performs the work that is associated with a specified work item.


## -prototype


````
WUDF_WORKITEM_FUNCTION OnWorkItem;

void OnWorkItem(
  _In_ IWDFWorkItem *pWorkItem
)
{ ... }

typedef void WUDF_WORKITEM_FUNCTION;
````


## -parameters




### -param *pWorkItem [in]

A pointer to an  <a href="..\wudfddi\nn-wudfddi-iwdfworkitem.md">IWDFWorkItem</a> interface.


## -returns



This callback function does not return a value.




## -remarks



To register an <i>OnWorkItem</i> callback function, your driver must place the callback function's address in a <a href="..\wudfworkitem\ns-wudfworkitem-_wudf_workitem_config.md">WUDF_WORKITEM_CONFIG</a> structure before calling <a href="https://msdn.microsoft.com/B34EABF4-C659-4DB4-AEC6-94F544D79221">IWDFDevice3::CreateWorkItem</a>.

Typically, a driver's <i>OnWorkItem</i> callback function performs tasks that are specified by information that the driver stored in the context memory of a work-item object.

The driver must not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560210">IWDFObject::DeleteWdfObject</a> from the <i>OnWorkItem</i> callback function.

For more information, see <a href="https://msdn.microsoft.com/4617A33F-9026-45FF-9CC2-7215423E6D35">Using Work Items</a>.


#### Examples

The function type is declared in <i>Wudfworkitem.h</i>, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
WUDF_WORKITEM_FUNCTION(
    _In_
    IWDFWorkItem* pWorkItem
    );

typedef WUDF_WORKITEM_FUNCTION *PFN_WUDF_WORKITEM;</pre>
</td>
</tr>
</table></span></div>
To define an <i>OnWorkItem</i> callback function that is named <i>MyWorkItem</i>, you must first provide a function declaration that SDV and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WUDF_WORKITEM_FUNCTION  MyWorkItem;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
  MyWorkItem (
   _In_
    IWDFWorkItem* pWorkItem
    )
  {…}
</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560210">IWDFObject::DeleteWdfObject</a>



<a href="..\wudfworkitem\ns-wudfworkitem-_wudf_workitem_config.md">WUDF_WORKITEM_CONFIG</a>



<a href="https://msdn.microsoft.com/B34EABF4-C659-4DB4-AEC6-94F544D79221">IWDFDevice3::CreateWorkItem</a>



 

 


