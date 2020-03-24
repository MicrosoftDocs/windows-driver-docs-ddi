---
UID: NF:wudfddi.IWDFDevice3.CreateWorkItem
title: IWDFDevice3::CreateWorkItem (wudfddi.h)
description: The CreateWorkItem method creates a framework work-item object, which can subsequently be added to the framework’s work-item queue.
old-location: wdf\iwdfdevice3_createworkitem.htm
tech.root: wdf
ms.assetid: B34EABF4-C659-4DB4-AEC6-94F544D79221
ms.date: 02/26/2018
keywords: ["IWDFDevice3::CreateWorkItem"]
ms.keywords: CreateWorkItem, CreateWorkItem method, CreateWorkItem method,IWDFDevice3 interface, IWDFDevice3 interface,CreateWorkItem method, IWDFDevice3.CreateWorkItem, IWDFDevice3::CreateWorkItem, umdf.iwdfdevice3_createworkitem, wdf.iwdfdevice3_createworkitem, wudfddi/IWDFDevice3::CreateWorkItem
f1_keywords:
 - "wudfddi/IWDFDevice3.CreateWorkItem"
req.header: wudfddi.h
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
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFDevice3.CreateWorkItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice3::CreateWorkItem


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateWorkItem</b> method creates a framework work-item object, which can subsequently be added to the framework’s work-item queue.


## -parameters




### -param pConfig [in]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfworkitem/ns-wudfworkitem-_wudf_workitem_config">WUDF_WORKITEM_CONFIG</a> structure that the driver must have already initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfworkitem/nf-wudfworkitem-wudf_workitem_config_init">WUDF_WORKITEM_CONFIG_INIT</a>.


### -param pParentObject [in, optional]

A pointer to the parent object interface or NULL.


### -param ppWorkItem [out]

A pointer to a buffer that receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfworkitem">IWDFWorkItem</a> interface for the new WorkItem object.


## -returns



The method returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



If you specify a parent object, the framework automatically deletes the work-item when the parent object is deleted. Alternatively, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfobject-deletewdfobject">IWDFObject::DeleteWdfObject</a> to delete a work-item. The driver must not delete a work-item in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfworkitem/nc-wudfworkitem-wudf_workitem_function">OnWorkItem</a> callback function.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-workitems">Using Work Items</a>.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WUDF_WORKITEM_CONFIG config;
        
WUDF_WORKITEM_CONFIG_INIT(&config, OnWorkItem); 
hr = m_IWdfDevice3->CreateWorkItem(&config,
                                   m_IWdfDevice3,   
                                   &m_WorkItem);
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice3">IWDFDevice3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfworkitem">IWDFWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfworkitem/nc-wudfworkitem-wudf_workitem_function">OnWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfworkitem/ns-wudfworkitem-_wudf_workitem_config">WUDF_WORKITEM_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfworkitem/nf-wudfworkitem-wudf_workitem_config_init">WUDF_WORKITEM_CONFIG_INIT</a>
 

 

