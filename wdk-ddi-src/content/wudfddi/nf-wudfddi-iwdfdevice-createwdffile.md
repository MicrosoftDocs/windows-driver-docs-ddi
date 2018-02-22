---
UID: NF:wudfddi.IWDFDevice.CreateWdfFile
title: IWDFDevice::CreateWdfFile method
author: windows-driver-content
description: The CreateWdfFile method creates a file object for a driver to use.
old-location: wdf\iwdfdevice_createwdffile.htm
old-project: wdf
ms.assetid: b356e3ac-451d-4a10-94e2-d03fcf76cb29
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: IWDFDevice, IWDFDevice interface, CreateWdfFile method, CreateWdfFile method, wdf.iwdfdevice_createwdffile, IWDFDevice::CreateWdfFile, umdf.iwdfdevice_createwdffile, CreateWdfFile method, IWDFDevice interface, CreateWdfFile, wudfddi/IWDFDevice::CreateWdfFile, UMDFDeviceObjectRef_d5f035e1-d7ea-474e-9dc4-bc6b64baea2c.xml
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFDevice.CreateWdfFile
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDevice::CreateWdfFile method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateWdfFile</b> method creates a file object for a driver to use.


## -syntax


````
HRESULT CreateWdfFile(
  [in, optional] LPCWSTR               pcwszFileName,
  [out]          IWDFDriverCreatedFile **ppFile
);
````


## -parameters




### -param pcwszFileName [in, optional]

A pointer to a <b>NULL</b>-terminated string that contains the name of the file to create a file object from. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not have to create the file object from a file name. If the driver must supply a name, the string that the driver passes must not contain any path separator characters ("/" or "\"). 


### -param ppFile [out]

A pointer to a buffer that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdrivercreatedfile.md">IWDFDriverCreatedFile</a> interface for the driver-created file object.


## -returns



<b>CreateWdfFile</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



For information about when a UMDF driver uses <b>CreateWdfFile</b> to handle I/O, see <a href="https://msdn.microsoft.com/3cd826fc-5c67-4ab4-800a-b5aa4bd5244f">Creating a File Object to Handle I/O</a>.

For information about when a UMDF driver might use <b>CreateWdfFile</b> to prevent an imbalance of create and close notifications to a driver, see <a href="https://msdn.microsoft.com/e6678226-44d3-4b1d-a296-2017bc9c7c37">Preventing an Imbalance of Create and Close Notifications to a Driver</a>. 




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfdrivercreatedfile.md">IWDFDriverCreatedFile</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice::CreateWdfFile method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

