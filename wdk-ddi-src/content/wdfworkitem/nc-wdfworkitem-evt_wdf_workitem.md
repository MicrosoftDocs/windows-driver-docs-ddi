---
UID: NC:wdfworkitem.EVT_WDF_WORKITEM
title: EVT_WDF_WORKITEM (wdfworkitem.h)
description: A driver's EvtWorkItem event callback function performs the work that is associated with a specified work item.
old-location: wdf\evtworkitem.htm
tech.root: wdf
ms.assetid: 2a2811de-9024-40a8-b8af-b61ca4100218
ms.date: 02/26/2018
keywords: ["EVT_WDF_WORKITEM callback function"]
ms.keywords: DFWorkItemObjectRef_e799d95c-bbde-402a-8ba6-6e03256772ff.xml, EVT_WDF_WORKITEM, EVT_WDF_WORKITEM callback, EvtWorkItem, EvtWorkItem callback function, kmdf.evtworkitem, wdf.evtworkitem, wdfworkitem/EvtWorkItem
req.header: wdfworkitem.h
req.include-header: Wdf.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_WORKITEM
 - wdfworkitem/EVT_WDF_WORKITEM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfworkitem.h
api_name:
 - EvtWorkItem
---

# EVT_WDF_WORKITEM callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtWorkItem</i> event callback function performs the work that is associated with a specified work item.

## -parameters

### -param WorkItem 

[in]
A handle to a framework work-item object.

## -remarks

Typically, a driver's <i>EvtWorkItem</i> callback function performs tasks that are specified by information that the driver stored in the context memory of a work-item object. 

To register an <i>EvtWorkItem</i> callback function, the driver calls <a href="/windows-hardware/drivers/ddi/wdfworkitem/nf-wdfworkitem-wdfworkitemcreate">WdfWorkItemCreate</a>.

After the <i>EvtWorkItem</i> callback function has performed the specified tasks, it must call <a href="/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectdelete">WdfObjectDelete</a>, unless the driver reuses work items. 

For more information about work items, see <a href="/windows-hardware/drivers/wdf/using-framework-work-items">Using Framework Work Items</a>.

The <i>EvtWorkItem</i> callback function runs at IRQL = PASSIVE_LEVEL in the context of a system worker thread.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectdelete">WdfObjectDelete</a>



<a href="/windows-hardware/drivers/ddi/wdfworkitem/nf-wdfworkitem-wdfworkitemcreate">WdfWorkItemCreate</a>



<a href="/windows-hardware/drivers/ddi/wdfworkitem/nf-wdfworkitem-wdfworkitemenqueue">WdfWorkItemEnqueue</a>