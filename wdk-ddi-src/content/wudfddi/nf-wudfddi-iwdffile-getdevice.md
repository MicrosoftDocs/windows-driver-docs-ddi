---
UID: NF:wudfddi.IWDFFile.GetDevice
title: IWDFFile::GetDevice method
author: windows-driver-content
description: The GetDevice method returns the interface to the device object that a file object is associated with.
old-location: wdf\iwdffile_getdevice.htm
old-project: wdf
ms.assetid: 914cc125-076e-40e1-baef-a12cba427b37
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetDevice method, GetDevice method, IWDFFile interface, GetDevice,IWDFFile.GetDevice, IWDFFile, IWDFFile interface, GetDevice method, IWDFFile::GetDevice, UMDFFileObjectRef_67417dd5-53be-487b-a93f-711bbcd6b0dd.xml, umdf.iwdffile_getdevice, wdf.iwdffile_getdevice, wudfddi/IWDFFile::GetDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFFile.GetDevice
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFFile::GetDevice method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDevice</b> method returns the interface to the device object that a file object is associated with.


## -syntax


````
void GetDevice(
  [out] IWDFDevice **ppWdfDevice
);
````


## -parameters




### -param ppWdfDevice [out]

A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a> interface for the device object that is associated with the file object.


## -returns



None




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>



 

 


