---
UID: NF:wudfddi.IWDFCmResourceList.GetDescriptor
title: IWDFCmResourceList::GetDescriptor (wudfddi.h)
description: The GetDescriptor method returns a pointer to a resource descriptor that is contained in this interface's resource list.
old-location: wdf\iwdfcmresourcelist_getdescriptor.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFCmResourceList::GetDescriptor"]
ms.keywords: GetDescriptor, GetDescriptor method, GetDescriptor method,IWDFCmResourceList interface, IWDFCmResourceList interface,GetDescriptor method, IWDFCmResourceList.GetDescriptor, IWDFCmResourceList::GetDescriptor, umdf.iwdfcmresourcelist_getdescriptor, wdf.iwdfcmresourcelist_getdescriptor, wudfddi/IWDFCmResourceList::GetDescriptor
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFCmResourceList::GetDescriptor
 - wudfddi/IWDFCmResourceList::GetDescriptor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFCmResourceList::GetDescriptor
---

# IWDFCmResourceList::GetDescriptor


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <b>GetDescriptor</b> method returns a pointer to a resource descriptor that is contained in this interface's resource list.

## -parameters

### -param Index

A zero-based index into the logical configuration that is contained in this interface's resource list.

## -returns

<b>GetDescriptor</b> returns a pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.

## -remarks

Drivers typically call <b>GetDescriptor</b> from within <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onpreparehardware">OnPrepareHardware</a>, before calling <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-mapiospace">MapIoSpace</a>.

The <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure  is defined in Wudfwdm.h.

For more information about parsing hardware resources, see <a href="/windows-hardware/drivers/wdf/finding-and-mapping-hardware-resources-in-umdf-1-x-drivers">Finding and Mapping Hardware Resources in a UMDF Driver</a>.


#### Examples

See example code in <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-mapiospace">IWDFDevice3::MapIoSpace</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfcmresourcelist">IWDFCmResourceList</a>

