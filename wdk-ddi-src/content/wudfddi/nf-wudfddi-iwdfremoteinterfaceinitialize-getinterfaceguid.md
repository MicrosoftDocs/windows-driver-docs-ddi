---
UID: NF:wudfddi.IWDFRemoteInterfaceInitialize.GetInterfaceGuid
title: IWDFRemoteInterfaceInitialize::GetInterfaceGuid (wudfddi.h)
description: The GetInterfaceGuid method retrieves the GUID that identifies a device interface.
old-location: wdf\iwdfremoteinterfaceinitialize_getinterfaceguid.htm
tech.root: wdf
ms.assetid: 3c68d458-9b34-4e45-993a-67f915347637
ms.date: 02/26/2018
ms.keywords: GetInterfaceGuid, GetInterfaceGuid method, GetInterfaceGuid method,IWDFRemoteInterfaceInitialize interface, IWDFRemoteInterfaceInitialize interface,GetInterfaceGuid method, IWDFRemoteInterfaceInitialize.GetInterfaceGuid, IWDFRemoteInterfaceInitialize::GetInterfaceGuid, UMDFIoTargetObjectRef_bbc014c0-b69e-4109-be81-a86d93104ad4.xml, umdf.iwdfremoteinterfaceinitialize_getinterfaceguid, wdf.iwdfremoteinterfaceinitialize_getinterfaceguid, wudfddi/IWDFRemoteInterfaceInitialize::GetInterfaceGuid
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
- IWDFRemoteInterfaceInitialize.GetInterfaceGuid
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFRemoteInterfaceInitialize::GetInterfaceGuid


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetInterfaceGuid</b> method retrieves the GUID that identifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a>. 


## -parameters




### -param pDeviceInterfaceGuid [out]

A pointer to a driver-allocated GUID structure that receives the device interface GUID.


## -returns



None.




## -remarks



For more information about the <b>GetInterfaceGuid</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF-based Drivers</a>.


#### Examples

The following code example shows how a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556775">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a> callback function can obtain the GUID that identifies the device interface that has arrived.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>void 
STDMETHODCALLTYPE
CMyDevice::OnRemoteInterfaceArrival(
    __in IWDFRemoteInterfaceInitialize  *FxRemoteInterfaceInit
    )
{
    GUID DeviceInterfaceGUID;
    FxRemoteInterfaceInit->GetInterfaceGuid(&DeviceInterfaceGUID);
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560232">IWDFRemoteInterfaceInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560242">IWDFRemoteInterfaceInitialize::RetrieveSymbolicLink</a>
 

 

