---
UID: NC:mrx.PMRX_CALLDOWN_CTX
title: PMRX_CALLDOWN_CTX (mrx.h)
description: Learn more about the PMRX_CALLDOWN_CTX callback function.
tech.root: ifsk
ms.date: 10/11/2023
keywords: ["PMRX_CALLDOWN_CTX callback function"]
ms.keywords: MRxStart, MRxStart routine [Installable File System Drivers], PMRX_CALLDOWN_CTX, ifsk.mrxstart, mrx/MRxStart, mrxref_e76b85d0-b290-4206-a16c-5d5ed9a5cfff.xml
req.header: mrx.h
req.include-header: Mrx.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PMRX_CALLDOWN_CTX
 - mrx/PMRX_CALLDOWN_CTX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_CALLDOWN_CTX
---

# PMRX_CALLDOWN_CTX callback function

## -description

The **MRxStart** routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to start the network mini-redirector.

## -parameters

### -param RxContext [in, out]

A pointer to the RX_CONTEXT structure. This parameter contains the IRP that requested the network mini-redirector to start.

### -param RxDeviceObject [in, out]

A pointer to the RDBSS_DEVICE_OBJECT structure for this network mini-redirector.

## -returns

**MRxStart** returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as one of the following:

| Return code | Description |
| ------------- | ------------- |
| STATUS_REDIRECTOR_STARTED | The network mini-redirector was already started. |
| STATUS_UNSUCCESSFUL | The network mini-redirector was unable to start successfully.

## -remarks

**MRxStart** completes the initialization of the network mini-redirector from the RDBSS perspective. Note that this is different from the initialization done in the **DriverEntry** routine. Any initialization that depends on RDBSS should be done as part of this routine while the initialization that is independent of RDBSS should be done in the **DriverEntry** routine.

Before calling **MRxStart**, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **MajorFunction** member is set to the major function of the IRP.

The **LowIoContext.ParamsFor.FsCtl.FsControlCode** member is set to the FSCTL code for the IRP if this was an FSTCL request used to start the network mini-redirector.

**MRxStart** is called by RDBSS from the [**RxStartMinirdr**](nf-mrx-rxstartminirdr.md) routine. Before calling **MRxStart**, RDBSS will register **RxDeviceObject** of the network mini-redirector as a file system. RDBSS will also register the network mini-redirector as a UNC provider if the network mini-redirector indicates support for UNC names.

If **MRxStart** returns STATUS_SUCCESS, then the routine was successful. Any other return value indicates that an error occurred in the startup sequence.

If **MRxStart** returns STATUS_SUCCESS, RDBSS sets the state of RDBSS to RDBSS_STARTED. This state is stored in the **StartStopContext.State** member of the RDBSS_DEVICE_OBJECT structure pointed to by **RxDeviceObject**.

A network mini-redirector would normally maintain an internal variable indicating whether the network mini-redirector is started. For example, a network mini-redirector might track when it is stopped, started, and when a start operation or stop operation is in progress.

## -see-also

[**MRxDevFcbXXXControlFile**](/windows-hardware/drivers/ifs/mrxdevfcbxxxcontrolfile)

[**MRxStop**](/windows-hardware/drivers/ifs/mrxstop)

[**RxStartMinirdr**](nf-mrx-rxstartminirdr.md)
