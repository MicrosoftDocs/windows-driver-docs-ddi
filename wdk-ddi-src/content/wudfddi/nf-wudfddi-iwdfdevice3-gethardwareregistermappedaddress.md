---
UID: NF:wudfddi.IWDFDevice3.GetHardwareRegisterMappedAddress
title: IWDFDevice3::GetHardwareRegisterMappedAddress (wudfddi.h)
description: A driver calls GetHardwareRegisterMappedAddress to get the user-mode mapped address of the memory resource it earlier mapped using MapIoSpace.
old-location: wdf\iwdfdevice3_gethardwareregistermappedaddress.htm
tech.root: wdf
ms.assetid: 94852404-301F-4C09-81D2-CEDEECFCD6BD
ms.date: 02/26/2018
keywords: ["IWDFDevice3::GetHardwareRegisterMappedAddress"]
ms.keywords: GetHardwareRegisterMappedAddress, GetHardwareRegisterMappedAddress method, GetHardwareRegisterMappedAddress method,IWDFDevice3 interface, IWDFDevice3 interface,GetHardwareRegisterMappedAddress method, IWDFDevice3.GetHardwareRegisterMappedAddress, IWDFDevice3::GetHardwareRegisterMappedAddress, umdf.iwdfdevice3_gethardwareregistermappedaddress, wdf.iwdfdevice3_gethardwareregistermappedaddress, wudfddi/IWDFDevice3::GetHardwareRegisterMappedAddress
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
 - IWDFDevice3::GetHardwareRegisterMappedAddress
 - wudfddi/IWDFDevice3::GetHardwareRegisterMappedAddress
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDevice3.GetHardwareRegisterMappedAddress
---

# IWDFDevice3::GetHardwareRegisterMappedAddress


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver calls <b>GetHardwareRegisterMappedAddress</b> to get the user-mode mapped address of the memory resource it earlier mapped using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-mapiospace">MapIoSpace</a>.

## -parameters

### -param PseudoBaseAddress 

[in]
A pointer to the pseudo base address returned by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-mapiospace">MapIoSpace</a>.

## -returns

User-mode base address of the resources mapped earlier using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-mapiospace">MapIoSpace</a>.

## -remarks

After the driver calls <b>GetHardwareRegisterMappedAddress</b>, it can access the user-mode address directly to read and write to the register.


<div class="alert"><b>Note</b>  This is not the recommended approach for accessing registers because it prevents UMDF from doing any validation on the access.</div>
<div> </div> For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reading-and-writing-to-device-registers-in-umdf-1-x-drivers">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.

If you do use <b>GetHardwareRegisterMappedAddress</b>, you must set the <b>UmdfRegisterAccessMode</b> INF directive to <b>RegisterAccessUsingUserModeMapping</b>.  For more information about UMDF  INF directives, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/specifying-wdf-directives-in-inf-files">Specifying WDF Directives in INF Files</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice3">IWDFDevice3</a>

