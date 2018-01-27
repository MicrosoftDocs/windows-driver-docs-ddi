---
UID: NF:wudfddi.IWDFDevice.AssignDeviceInterfaceState
title: IWDFDevice::AssignDeviceInterfaceState method
author: windows-driver-content
description: The AssignDeviceInterfaceState method enables or disables the specified device interface instance for a device.
old-location: wdf\iwdfdevice_assigndeviceinterfacestate.htm
old-project: wdf
ms.assetid: 466af310-f2a7-4bd7-b927-df644e2e9c24
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iwdfdevice_assigndeviceinterfacestate, IWDFDevice::AssignDeviceInterfaceState, AssignDeviceInterfaceState method, IWDFDevice interface, IWDFDevice, umdf.iwdfdevice_assigndeviceinterfacestate, IWDFDevice interface, AssignDeviceInterfaceState method, UMDFDeviceObjectRef_d3c15e61-9df6-4b55-a479-375486383064.xml, AssignDeviceInterfaceState, wudfddi/IWDFDevice::AssignDeviceInterfaceState, AssignDeviceInterfaceState method
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
-	IWDFDevice.AssignDeviceInterfaceState
product: Windows
targetos: Windows
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDevice::AssignDeviceInterfaceState method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>AssignDeviceInterfaceState</b> method enables or disables the specified device interface instance for a device.


## -syntax


````
HRESULT AssignDeviceInterfaceState(
  [in]           LPCGUID pDeviceInterfaceGuid,
  [in, optional] PCWSTR  pReferenceString,
  [in]           BOOL    Enable
);
````


## -parameters




### -param pDeviceInterfaceGuid [in]

A pointer to the GUID for a device interface class.


### -param pReferenceString [in, optional]

A pointer to a <b>NULL</b>-terminated string that contains the name of the instance of the device interface. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not have to supply a name. If the driver must supply a name, the string that the driver passes must not contain any path separator characters ("/" or "\"). 


### -param Enable [in]

A BOOL value that specifies whether the device interface instance should be enabled or disabled. <b>TRUE</b> indicates to enable; <b>FALSE</b> indicates to disable.


## -returns


<b>AssignDeviceInterfaceState</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.



## -remarks


If <a href="https://msdn.microsoft.com/library/windows/hardware/ff557016">IWDFDevice::CreateDeviceInterface</a> succeeds, the framework automatically enables and disables the interface based on the device's PnP state.

Use the <b>AssignDeviceInterfaceState</b> method to disable and re-enable a device interface manually.



For more information about device interfaces, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF Drivers</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557016">IWDFDevice::CreateDeviceInterface</a>

<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice::AssignDeviceInterfaceState method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

