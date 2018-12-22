---
UID: NI:gnssdriver.IOCTL_GNSS_EXECUTE_CWTEST
title: IOCTL_GNSS_EXECUTE_CWTEST
description: The IOCTL_GNSS_EXECUTE_CWTEST control code is used by the GNSS manufacturing test application to start a carrier wave test and get the measurement. The test application must wait for the result before starting another iteration of the measurement.
old-location: gnss\ioctl_gnss_execute_cwtest.htm
tech.root: gnss
ms.assetid: 36AFBB03-9F01-4CA7-A5E8-C6F744984B6F
ms.date: 02/15/2018
ms.keywords: IOCTL_GNSS_EXECUTE_CWTEST, IOCTL_GNSS_EXECUTE_CWTEST control, IOCTL_GNSS_EXECUTE_CWTEST control code [Sensor Devices], gnss.ioctl_gnss_execute_cwtest, gnssdriver/IOCTL_GNSS_EXECUTE_CWTEST
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
-	IOCTL_GNSS_EXECUTE_CWTEST
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_EXECUTE_CWTEST IOCTL


## -description


The <b>IOCTL_GNSS_EXECUTE_CWTEST</b> control code is used by the GNSS manufacturing test application to start a carrier wave test and get the measurement. The test application must wait for the result before starting another iteration of the measurement.


## -ioctlparameters




### -input-buffer

Set to NULL.


### -input-buffer-length

Set to 0.


### -output-buffer

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn925102">GNSS_CWTESTDATA</a> structure.


### -output-buffer-length

Set to sizeof(GNSS_CWTESTDATA).


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



<h3><a id="GNSS_test_application_notes"></a><a id="gnss_test_application_notes"></a><a id="GNSS_TEST_APPLICATION_NOTES"></a>GNSS test application notes</h3>
The test application must ensure that no more than one carrier wave test is started at the same time.

Once the carrier wave test is started, the test application must wait for the result.

The test application will need to repeat this command if it wants to retrieve more than one measurement.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
The GNSS driver must fail the new carrier wave test session request if there is already a test in progress.

Once the GNSS driver accepts the carrier wave test session parameters, validates them and starts the detection in the GNSS engine. When the measurements are received, the driver immediately completes the IO with a return code and the measurements.

The GNSS stack must return the measurements as soon as they are available.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

