---
UID: NF:wudfddi.IWDFDevice3.UnmapIoSpace
title: IWDFDevice3::UnmapIoSpace (wudfddi.h)
description: The UnmapIoSpace method unmaps a specified range of physical addresses previously mapped by MapIoSpace method.
old-location: wdf\iwdfdevice3_unmapiospace.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFDevice3::UnmapIoSpace"]
ms.keywords: IWDFDevice3 interface,UnmapIoSpace method, IWDFDevice3.UnmapIoSpace, IWDFDevice3::UnmapIoSpace, UnmapIoSpace, UnmapIoSpace method, UnmapIoSpace method,IWDFDevice3 interface, umdf.iwdfdevice3_unmapiospace, wdf.iwdfdevice3_unmapiospace, wudfddi/IWDFDevice3::UnmapIoSpace
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
 - IWDFDevice3::UnmapIoSpace
 - wudfddi/IWDFDevice3::UnmapIoSpace
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDevice3::UnmapIoSpace
---

# IWDFDevice3::UnmapIoSpace


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>UnmapIoSpace</b> method unmaps a specified range of physical addresses previously mapped by <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-mapiospace">MapIoSpace</a> method.

## -parameters

### -param PseudoBaseAddress [in]


Pointer to the pseudo base address obtained from a previous call to <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-mapiospace">MapIoSpace</a> method to which the physical address range was mapped.

### -param NumberOfBytes [in]


Specifies the number of bytes that were mapped.

## -remarks

If a driver calls <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-mapiospace">MapIoSpace</a> in <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onpreparehardware">OnPrepareHardware</a> callback. It calls <b>UnmapIoSpace</b> in its <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onreleasehardware">OnReleaseHardware</a> callback.

For an example, see <a href="/windows-hardware/drivers/wdf/finding-and-mapping-hardware-resources-in-umdf-1-x-drivers">Finding and Mapping Hardware Resources in a UMDF Driver</a>.


#### Examples

See example code in <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-mapiospace">IWDFDevice3::MapIoSpace</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice3">IWDFDevice3</a>

