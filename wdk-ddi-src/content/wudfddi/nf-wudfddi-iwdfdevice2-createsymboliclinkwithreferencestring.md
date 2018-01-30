---
UID: NF:wudfddi.IWDFDevice2.CreateSymbolicLinkWithReferenceString
title: IWDFDevice2::CreateSymbolicLinkWithReferenceString method
author: windows-driver-content
description: TheCreateSymbolicLinkWithReferenceString method creates a symbolic link name, and optionally, a reference string, for a device.
old-location: wdf\iwdfdevice2_createsymboliclinkwithreferencestring.htm
old-project: wdf
ms.assetid: bce932a6-2f73-4d0e-8616-45fd41abb776
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: CreateSymbolicLinkWithReferenceString method, IWDFDevice2 interface, wdf.iwdfdevice2_createsymboliclinkwithreferencestring, IWDFDevice2 interface, CreateSymbolicLinkWithReferenceString method, umdf.iwdfdevice2_createsymboliclinkwithreferencestring, UMDFDeviceObjectRef_40f806fa-5db7-48db-b3c7-0f338947887e.xml, CreateSymbolicLinkWithReferenceString, wudfddi/IWDFDevice2::CreateSymbolicLinkWithReferenceString, CreateSymbolicLinkWithReferenceString method, IWDFDevice2, IWDFDevice2::CreateSymbolicLinkWithReferenceString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
-	IWDFDevice2.CreateSymbolicLinkWithReferenceString
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFDevice2::CreateSymbolicLinkWithReferenceString method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The<b>CreateSymbolicLinkWithReferenceString</b> method creates a symbolic link name, and optionally, a reference string, for a device 


## -syntax


````
HRESULT CreateSymbolicLinkWithReferenceString(
  [in]           PCWSTR pSymbolicLink,
  [in, optional] PCWSTR pReferenceString
);
````


## -parameters




### -param pSymbolicLink [in]

A pointer to a <b>NULL</b>-terminated character string that becomes the user-visible name of the device. The symbolic link name must be in the global <b>DosDevices</b> namespace.


### -param pReferenceString [in, optional]

A pointer to a <b>NULL</b>-terminated character string that Windows appends to the device name when an application uses the symbolic name that the <i>pSymbolicLink</i> parameter specifies. For more information, see the following Remarks section. This parameter is optional and can be <b>NULL</b>.


## -returns


<b>CreateSymbolicLinkWithReferenceString</b> returns S_OK if the operation succeeds. Otherwise, the method might return one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The caller specified an invalid value for an input parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The memory allocation failed.

</td>
</tr>
</table> 

This method might return one of the other values that Winerror.h contains.



## -remarks


<b>CreateSymbolicLinkWithReferenceString</b> creates a symbolic link name, and optionally a reference string, for the device that the <a href="..\wudfddi\nn-wudfddi-iwdfdevice2.md">IWDFDevice2</a> interface represents. After a driver calls <b>CreateSymbolicLinkWithReferenceString</b>, applications can use the symbolic link name to access the device.

Suppose your device's name is "\Device\MyDevice". You can create a symbolic link name of "DeviceUserName" for your device by specifying "L"DeviceUserName"" for the <i>pSymbolicLink</i> parameter. If you specify "L"Instance3"" for the <i>pReferenceString</i> parameter, you are creating a symbolic link to \Device\MyDevice\Instance3. If an application opens the device by using the symbolic link name, the I/O manager opens \Device\MyDevice and creates a WDM file object that contains the \Instance3 string as the file name. Your UMDF-based driver receives a framework-created file object, which also contains the \Instance3 string as the file name (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558939">IWDFFile::RetrieveFileName</a>). 

Typically, instead of providing symbolic links, framework-based drivers provide <a href="https://msdn.microsoft.com/0a88cbb6-66be-4ef7-93da-27d7ce169779">device interfaces</a> that applications can use to access their devices.

If the device is removed unexpectedly (surprise-removed), the framework removes the symbolic link to the device. The driver can then use the symbolic link name for a new instance of the device. 

If you do not need to add a reference string to your device's symbolic link name, your driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff557023">IWDFDevice::CreateSymbolicLink</a> instead of <b>CreateSymbolicLinkWithReferenceString</b>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557023">IWDFDevice::CreateSymbolicLink</a>

<a href="..\wudfddi\nn-wudfddi-iwdfdevice2.md">IWDFDevice2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice2::CreateSymbolicLinkWithReferenceString method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

