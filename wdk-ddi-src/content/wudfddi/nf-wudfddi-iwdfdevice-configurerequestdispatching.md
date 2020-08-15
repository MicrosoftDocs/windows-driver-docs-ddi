---
UID: NF:wudfddi.IWDFDevice.ConfigureRequestDispatching
title: IWDFDevice::ConfigureRequestDispatching (wudfddi.h)
description: The ConfigureRequestDispatching method configures the queuing of I/O requests of the specified type to the specified I/O queue.
old-location: wdf\iwdfdevice_configurerequestdispatching.htm
tech.root: wdf
ms.assetid: b3318695-e9f2-480a-9133-9008ef0002b7
ms.date: 02/26/2018
keywords: ["IWDFDevice::ConfigureRequestDispatching"]
ms.keywords: ConfigureRequestDispatching, ConfigureRequestDispatching method, ConfigureRequestDispatching method,IWDFDevice interface, IWDFDevice interface,ConfigureRequestDispatching method, IWDFDevice.ConfigureRequestDispatching, IWDFDevice::ConfigureRequestDispatching, UMDFDeviceObjectRef_1fbf31c6-856c-45d2-aa86-3b36372821c8.xml, umdf.iwdfdevice_configurerequestdispatching, wdf.iwdfdevice_configurerequestdispatching, wudfddi/IWDFDevice::ConfigureRequestDispatching
f1_keywords:
 - "wudfddi/IWDFDevice.ConfigureRequestDispatching"
 - "IWDFDevice.ConfigureRequestDispatching"
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
- IWDFDevice.ConfigureRequestDispatching
targetos: Windows
req.typenames: 
---

# IWDFDevice::ConfigureRequestDispatching


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>ConfigureRequestDispatching</b> method configures the queuing of I/O requests of the specified type to the specified I/O queue.


## -parameters




### -param pQueue 
[in]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a> interface for the I/O queue to configure. 


### -param RequestType 
[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WDF_REQUEST_TYPE</a>-typed value that identifies the request type to be queued. The only valid <b>WDF_REQUEST_TYPE</b> values are <b>WdfRequestCreate</b>, <b>WdfRequestRead</b>, <b>WdfRequestWrite</b>, and <b>WdfRequestDeviceIoControl</b>.


### -param Forward 
[in]
A BOOL value that specifies whether requests of the specified type are queued. <b>TRUE</b> indicates to enable queuing requests; <b>FALSE</b> indicates to disable queuing requests.


## -returns



<b>ConfigureRequestDispatching</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WDF_REQUEST_TYPE</a>
 

 

