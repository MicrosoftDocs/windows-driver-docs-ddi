---
UID: NI:gnssdriver.IOCTL_GNSS_EXECUTE_SELFTEST
title: IOCTL_GNSS_EXECUTE_SELFTEST
author: windows-driver-content
description: The IOCTL_GNSS_EXECUTE_SELFTEST control code is used by the GNSS manufacturing test application to initiate a self test in the GNSS lower stack.
old-location: gnss\ioctl_gnss_execute_selftest.htm
tech.root: gnss
ms.assetid: EAD10523-FFA0-4B08-BCBD-A20C90A1B8F6
ms.date: 02/15/2018
ms.keywords: IOCTL_GNSS_EXECUTE_SELFTEST, IOCTL_GNSS_EXECUTE_SELFTEST control, IOCTL_GNSS_EXECUTE_SELFTEST control code [Sensor Devices], gnss.ioctl_gnss_execute_selftest, gnssdriver/IOCTL_GNSS_EXECUTE_SELFTEST
ms.topic: ioctl
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	IOCTL_GNSS_EXECUTE_SELFTEST
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_EXECUTE_SELFTEST IOCTL


## -description


The <b>IOCTL_GNSS_EXECUTE_SELFTEST</b> control code is used by the GNSS manufacturing test application to initiate a self test in the GNSS lower stack.


## -ioctlparameters




### -input-buffer

A pointer to a <b>GNSS_SELFTESTCONFIG</b> structure.


### -input-buffer-length

Set to sizeof(GNSS_SELFTESTCONFIG).




### -output-buffer

A pointer to a <b>GNSS_SELFTESTRESULT</b> structure.




### -output-buffer-length

Set to sizeof(GNSS_SELFTESTRESULT).




### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



<h3><a id="GNSS_test_application_notes"></a><a id="gnss_test_application_notes"></a><a id="GNSS_TEST_APPLICATION_NOTES"></a>GNSS test application notes</h3>
The GNSS test application must wait for a status response from the test, and be resilient to the GNSS driver not responding.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
The GNSS driver must fail a new self test session request if there is already a test in progress.

Once the GNSS driver accepts the self test session parameters, validates them and starts the test in the GNSS engine. The GNSS driver completes the I/O request after completing the tests and returning the status to the GNSS test application.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

