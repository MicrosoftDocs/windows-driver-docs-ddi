---
UID: NS:video._VIDEO_PORT_DEBUG_REPORT_INTERFACE
title: _VIDEO_PORT_DEBUG_REPORT_INTERFACE (video.h)
description: The VIDEO_PORT_DEBUG_REPORT_INTERFACE structure holds pointers to the Debug Report functions, which are implemented by the video port driver.
old-location: display\video_port_debug_report_interface.htm
tech.root: display
ms.assetid: 11536f1e-523c-4796-a973-e53291c756a8
ms.date: 05/10/2018
keywords: ["VIDEO_PORT_DEBUG_REPORT_INTERFACE structure"]
ms.keywords: PVIDEO_PORT_DEBUG_REPORT_INTERFACE, PVIDEO_PORT_DEBUG_REPORT_INTERFACE structure pointer, *PVIDEO_PORT_DEBUG_REPORT_INTERFACE, VIDEO_PORT_DEBUG_REPORT_INTERFACE, VIDEO_PORT_DEBUG_REPORT_INTERFACE structure, Video_Structs_4db5be2e-169d-4487-b979-e75cd1b2cb18.xml, _VIDEO_PORT_DEBUG_REPORT_INTERFACE, display.video_port_debug_report_interface, video/PVIDEO_PORT_DEBUG_REPORT_INTERFACE, video/VIDEO_PORT_DEBUG_REPORT_INTERFACE
f1_keywords:
 - "video/VIDEO_PORT_DEBUG_REPORT_INTERFACE"
 - "VIDEO_PORT_DEBUG_REPORT_INTERFACE"
req.header: video.h
req.include-header: Video.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- video.h
api_name:
- VIDEO_PORT_DEBUG_REPORT_INTERFACE
targetos: Windows
req.typenames: VIDEO_PORT_DEBUG_REPORT_INTERFACE, *PVIDEO_PORT_DEBUG_REPORT_INTERFACE
---

# _VIDEO_PORT_DEBUG_REPORT_INTERFACE structure


## -description


The VIDEO_PORT_DEBUG_REPORT_INTERFACE structure holds pointers to the Debug Report functions, which are implemented by the video port driver.


## -struct-fields




### -field Size

Specifies the size, in bytes, of this structure.


### -field Version

Specifies the version of the interface returned by the video port driver. Currently, the only supported version is VIDEO_PORT_DEBUG_REPORT_INTERFACE_VERSION_1.


### -field Context

Pointer to a context that is provided by the video port driver.


### -field InterfaceReference

Pointer to an interface reference function that is implemented by the video port driver.


### -field InterfaceDereference

Pointer to an interface dereference function that is implemented by the video port driver.


## -remarks



The following describes the callback functions in more detail.

### DbgReportComplete

The DbgReportComplete function closes an error report and frees any resources associated with the report.

If your display miniport driver detects a failure and then recovers from it, you can create an error report that can later be used for debugging. First, call DbgReportCreate to create an initial report. Then add data to the report by making one or more calls to DbgReportSecondaryData. When you have finished adding data to the report, call DbgReportComplete.

This function is available in Windows Vista and later operating systems.

**Syntax**

```cpp
VOID DbgReportComplete(
   IN OUT DXGK_DEBUG_REPORT_HANDLE hReport
);
```

**Parameters**

* *hReport* A handle to the error report that is to be closed. The display miniport driver previously obtained this handle by calling DbgReportCreate.



### DbgReportCreate

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_debug_report_interface">DbgReportCreate</a> creates an entry in the system event log and displays a dialog box that informs the user of the failure and presents the opportunity to upload an error report to Microsoft.

The DbgReportCreate function creates an initial error report.

This function is available in Windows Vista and later operating systems.

**Syntax**

```cpp
DXGK_DEBUG_REPORT_HANDLE (*DbgReportCreate)(
  _In_ HANDLE    DeviceHandle,
  _In_ ULONG     ulCode,
  _In_ ULONG_PTR ulpArg1,
  _In_ ULONG_PTR ulpArg2,
  _In_ ULONG_PTR ulpArg3,
  _In_ ULONG_PTR ulpArg4
);
```

**Parameters**

* *DeviceHandle [in]*
A handle to a context block associated with a display adapter. The display miniport driver created this handle in its DxgkDdiAddDevice function. This parameter can be NULL.
* *ulCode [in]* A code for the error report. The following codes are supported: THREAD_STUCK_IN_DEVICE_DRIVER VIDEO_DRIVER_DEBUG_REPORT_REQUEST, VIDEO_TDR_FATAL_ERROR, and  VIDEO_TDR_SUCCESS.
* *ulpArg1 [in]* The first argument to be added to the report. The developer of the display miniport driver determines the value and meaning of ulpArg1.
* *ulpArg2 [in]* The second argument to be added to the report. The developer of the display miniport driver determines the value and meaning of ulpArg2.
* *ulpArg3 [in]* The third argument to be added to the report. The developer of the display miniport driver determines the value and meaning of ulpArg3.
* *ulpArg4 [in]* Reserved


The error report is saved in a file and scheduled to be sent to Microsoft when the computer is rebooted. The error report contains an error code and four arguments. The error code and the first three arguments are provided by the caller of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_debug_report_interface">DbgReportCreate</a>. The fourth argument in the report is provided by the operating system and indicates the number of reports generated since the computer was started. For example, if the value of the fourth argument is 5, this means that four previous error reports were generated by the display miniport driver since the computer was last started. Only the fifth report is saved because each report overwrites the previous one.

### DbgReportSecondaryData

The DbgReportSecondaryData function appends data to an initial error report that was previously created by DbgReportCreate.

This function is available in Windows Vista and later operating systems.

**Syntax**

```cpp
BOOLEAN (*DbgReportSecondaryData)(
  _Inout_ DXGK_DEBUG_REPORT_HANDLE hReport,
  _In_    PVOID                    pvData,
  _In_    ULONG                    ulDataSize
);
```

**Parameters**

* *hReport [in, out]* A handle to the error report to which data will be appended. The display miniport driver previously obtained this handle by calling DbgReportCreate.
* *pvData [in]* A pointer to a buffer that holds the data to be added to the report.
* *ulDataSize [in]* The size, in bytes, of the data to be added to the report. The value of this parameter must be less than or equal to DXGK_DEBUG_REPORT_MAX_SIZE.


If DbgReportSecondaryData succeeds, it returns <b>TRUE</b>. Otherwise, it returns <b>FALSE</b>.

Call DbgReportSecondaryData to add data to an initial report that was created by a previous call to DbgReportCreate. You can call DbgReportSecondaryData several times, but with each call, the data written to the report overwrites the data written by the previous call. The following steps give a good strategy for incrementally adding data to the report.

1. Obtain the data that is safest to collect. 
2. Call DbgReportSecondaryData to write that data to the report.
3. Obtain data that is more risky to collect. 
4. Call DbgReportSecondaryData to write the original safe data along with the newly collected risky data to the report. You must include both the safe and the risky data in this call because the data written by this call overwrites the data written by the first call to DbgReportSecondaryData. 
5. Continue calling DbgReportSecondaryData, enhancing the data each time, until you have no more data to add. 
6. When you have finished adding data to the report, close the report by calling DbgReportComplete. The report is stored in a file and sent to Microsoft when the computer is rebooted.
7. If the computer stops responding before you call DbgReportComplete, the data added to the report by the most recent successful call to DbgReportSecondaryData is saved and then sent to Microsoft when the computer is rebooted.



This structure is available in the following operating systems:

* Windows Server 2003 SP1 and subsequent service packs
* Windows XP SP2 and subsequent service packs



The video miniport driver supplies the <b>Size</b> and <b>Version</b> members of this structure, and then calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueryservices">VideoPortQueryServices</a>, which initializes the remaining members of this structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_debug_report_interface">DbgReportComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_debug_report_interface">DbgReportCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_debug_report_interface">DbgReportSecondaryData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueryservices">VideoPortQueryServices</a>
 

 

