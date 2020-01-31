---
UID: NF:wudfddi.IWDFDevice.CreateSymbolicLink
title: IWDFDevice::CreateSymbolicLink (wudfddi.h)
description: The CreateSymbolicLink method creates a symbolic link for the device.
old-location: wdf\iwdfdevice_createsymboliclink.htm
tech.root: wdf
ms.assetid: 15984217-e789-457c-b20f-c3d51741f5d3
ms.date: 02/26/2018
ms.keywords: CreateSymbolicLink, CreateSymbolicLink method, CreateSymbolicLink method,IWDFDevice interface, IWDFDevice interface,CreateSymbolicLink method, IWDFDevice.CreateSymbolicLink, IWDFDevice::CreateSymbolicLink, UMDFDeviceObjectRef_20b93e0a-a676-44f7-bbd0-d2749dd7a0b8.xml, umdf.iwdfdevice_createsymboliclink, wdf.iwdfdevice_createsymboliclink, wudfddi/IWDFDevice::CreateSymbolicLink
f1_keywords:
 - "wudfddi/IWDFDevice.CreateSymbolicLink"
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
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
- IWDFDevice.CreateSymbolicLink
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice::CreateSymbolicLink


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateSymbolicLink</b> method creates a symbolic link for the device.


## -parameters




### -param pSymbolicLink [in]

A pointer to a <b>NULL</b>-terminated string that contains the name of the symbolic link for the device. The symbolic link name must be in the global <b>DosDevices</b> namespace.


## -returns



<b>CreateSymbolicLink</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks




        A symbolic link is a file-system object that points to another file-system object. The object being pointed to is called the target.

For an example usage of this method, see the <a href="https://go.microsoft.com/fwlink/p/?LinkId=617963">VirtualSerial</a> driver sample.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-createsymboliclinkwithreferencestring">IWDFDevice2::CreateSymbolicLinkWithReferenceString</a>
 

 

