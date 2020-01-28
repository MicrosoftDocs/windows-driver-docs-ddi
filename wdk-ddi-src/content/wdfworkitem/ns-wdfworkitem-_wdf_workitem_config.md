---
UID: NS:wdfworkitem._WDF_WORKITEM_CONFIG
title: _WDF_WORKITEM_CONFIG (wdfworkitem.h)
description: The WDF_WORKITEM_CONFIG structure contains information that is associated with a work item.
old-location: wdf\wdf_workitem_config.htm
tech.root: wdf
ms.assetid: b6186c05-ccb9-432c-bd83-9a3fb3af7f0b
ms.date: 02/26/2018
ms.keywords: "*PWDF_WORKITEM_CONFIG, DFWorkItemObjectRef_48012621-6363-421b-8b95-2bdae4e63b32.xml, PWDF_WORKITEM_CONFIG, PWDF_WORKITEM_CONFIG structure pointer, WDF_WORKITEM_CONFIG, WDF_WORKITEM_CONFIG structure, _WDF_WORKITEM_CONFIG, kmdf.wdf_workitem_config, wdf.wdf_workitem_config, wdfworkitem/PWDF_WORKITEM_CONFIG, wdfworkitem/WDF_WORKITEM_CONFIG"
f1_keywords:
 - "wdfworkitem/WDF_WORKITEM_CONFIG"
req.header: wdfworkitem.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
- HeaderDef
api_location:
- wdfworkitem.h
api_name:
- WDF_WORKITEM_CONFIG
product:
- Windows
targetos: Windows
req.typenames: WDF_WORKITEM_CONFIG, *PWDF_WORKITEM_CONFIG
---

# _WDF_WORKITEM_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_WORKITEM_CONFIG</b> structure contains information that is associated with a work item.


## -struct-fields




### -field Size

The size, in bytes, of this <b>WDF_WORKITEM_CONFIG</b> structure.


### -field EvtWorkItemFunc

The address of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a> event callback function.


### -field AutomaticSerialization

A Boolean value that, if <b>TRUE</b>, indicates that the framework will synchronize execution of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a> callback function with callback functions from other objects that are underneath the work-item object's parent object. For more information, see the following Remarks section. If <b>FALSE</b>, the framework does not synchronize execution of the <i>EvtWorkItem</i> callback function.


## -remarks



Your driver must initialize the <b>WDF_WORKITEM_CONFIG</b> structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfworkitem/nf-wdfworkitem-wdf_workitem_config_init">WDF_WORKITEM_CONFIG_INIT</a>. Your driver can then pass the structure to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfworkitem/nf-wdfworkitem-wdfworkitemcreate">WdfWorkItemCreate</a> method as an input parameter.

Setting the <b>AutomaticSerialization</b> member of <b>WDF_WORKITEM_CONFIG</b> to <b>TRUE</b> has no effect if the parent object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ne-wdfobject-_wdf_synchronization_scope">synchronization scope</a> is set to <b>WdfSynchronizationScopeNone</b>.

If <b>AutomaticSerialization</b> is <b>TRUE</b>, the parent object's execution level must be <b>WdfExecutionLevelPassive</b>.

For more information about <b>AutomaticSerialization</b> and synchronizing driver callback functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfworkitem/nf-wdfworkitem-wdf_workitem_config_init">WDF_WORKITEM_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfworkitem/nf-wdfworkitem-wdfworkitemcreate">WdfWorkItemCreate</a>
 

 

