---
UID: NF:wudfddi.IWDFIoQueue.RetrieveNextRequestByFileObject
title: IWDFIoQueue::RetrieveNextRequestByFileObject (wudfddi.h)
description: The RetrieveNextRequestByFileObject method retrieves from an I/O queue the next I/O request whose file object matches the specified file object.
old-location: wdf\iwdfioqueue_retrievenextrequestbyfileobject.htm
tech.root: wdf
ms.date: 08/12/2022
keywords: ["IWDFIoQueue::RetrieveNextRequestByFileObject"]
ms.keywords: IWDFIoQueue interface,RetrieveNextRequestByFileObject method, IWDFIoQueue.RetrieveNextRequestByFileObject, IWDFIoQueue::RetrieveNextRequestByFileObject, RetrieveNextRequestByFileObject, RetrieveNextRequestByFileObject method, RetrieveNextRequestByFileObject method,IWDFIoQueue interface, UMDFQueueObjectRef_15af6c6e-0a40-41bd-9b76-fb7c206bc937.xml, umdf.iwdfioqueue_retrievenextrequestbyfileobject, wdf.iwdfioqueue_retrievenextrequestbyfileobject, wudfddi/IWDFIoQueue::RetrieveNextRequestByFileObject
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFIoQueue::RetrieveNextRequestByFileObject
 - wudfddi/IWDFIoQueue::RetrieveNextRequestByFileObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoQueue::RetrieveNextRequestByFileObject
---

# IWDFIoQueue::RetrieveNextRequestByFileObject

## -description

> [!WARNING]
> UMDF 2 is the latest version of UMDF and supersedes UMDF 1. All new UMDF drivers should be written using UMDF 2. No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10. Universal Windows drivers must use UMDF 2. For more info, see [Getting Started with UMDF](/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2).

The **RetrieveNextRequestByFileObject** method retrieves from an I/O queue the next I/O request whose file object matches the specified file object.

## -parameters

### -param pFile [in]

A pointer to the [IWDFFile](./nn-wudfddi-iwdffile.md) interface for the file object that is used to retrieve the next I/O request whose file object matches this supplied file object.

### -param ppRequest [out]

A pointer to a buffer that receives a pointer to the [IWDFIoRequest](./nn-wudfddi-iwdfiorequest.md) interface for the next request object whose file object matches the supplied file object, or receives **NULL** if the queue is empty or if the next request is not found.

## -returns

**RetrieveNextRequestByFileObject** returns one of the following values:

| Return code | Description |
|--|--|
| **S_OK** | The next I/O request was successfully retrieved from the I/O queue. |
| **HRESULT_FROM_NT(STATUS_WDF_PAUSED)** | The queue is not dispatching requests. This situation occurs if the device undergoes a power state transition and all of the queues are stopped from dispatching requests or if the driver explicitly called IWDFIoQueue::Stop to stop dispatching requests. This situation can also occur if the driver attempts to remove a request from a manual queue that is power managed and that is powered down or if the queue is paused. |
| **HRESULT_FROM_WIN32(ERROR_NO_MORE_ITEMS)** | No requests were in the queue. |
| **HRESULT_FROM_NT(STATUS_INVALID_DEVICE_STATE)** | The call was made to retrieve the request from a parallel queue. |

**RetrieveNextRequestByFileObject** might also return other HRESULT values.

## -remarks

If a driver configures an I/O queue for manual dispatching of I/O requests, the driver can call the **RetrieveNextRequestByFileObject** method to obtain the next request whose file object matches the supplied file object from the queue. For more information about manually dispatching I/O requests, see [Configuring Dispatch Mode for an I/O Queue](/windows-hardware/drivers/wdf/configuring-dispatch-mode-for-an-i-o-queue).

If multiple I/O requests whose file objects match the file object that the *pFile* parameter points to exist in the I/O queue, the first I/O request is returned.

### Examples

For a code example of how to use the **RetrieveNextRequestByFileObject** method, see [IWDFIoQueue::RetrieveNextRequest](./nf-wudfddi-iwdfioqueue-retrievenextrequest.md).

## -see-also

- [IWDFFile](./nn-wudfddi-iwdffile.md)
- [IWDFIoQueue](./nn-wudfddi-iwdfioqueue.md)
- [IWDFIoQueue::RetrieveNextRequest](./nf-wudfddi-iwdfioqueue-retrievenextrequest.md)
- [IWDFIoQueue::Stop](./nf-wudfddi-iwdfioqueue-stop.md)
- [IWDFIoRequest](./nn-wudfddi-iwdfiorequest.md)
