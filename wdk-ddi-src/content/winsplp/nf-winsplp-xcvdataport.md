---
UID: NF:winsplp.XcvDataPort
title: XcvDataPort function (winsplp.h)
description: A port monitor server DLL's XcvDataPort function receives information from, and returns information to, the port monitor's UI DLL.
tech.root: print
ms.date: 03/09/2023
keywords: ["XcvDataPort function"]
ms.keywords: print.xcvdataport, winsplp/XcvDataPort, XcvDataPort, spoolfnc_09b26a0a-26ad-43c9-995a-99cd4fb4a726.xml, XcvDataPort function [Print Devices]
req.header: winsplp.h
req.include-header: Winsplp.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
f1_keywords:
 - XcvDataPort
 - winsplp/XcvDataPort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winsplp.h
api_name:
 - XcvDataPort
---

## -description

A port monitor server DLL's **XcvDataPort** function receives information from, and returns information to, the port monitor's UI DLL.

## -parameters

### -param hXcv [in]

Caller-supplied printer handle, obtained by calling **OpenPrinter** (described in the Microsoft Windows SDK documentation). This handle is created and returned by the [XcvOpenPort](..\winsplp\nf-winsplp-xcvopenport.md) function.

### -param pszDataName [in]

Caller-supplied pointer to a string representing the name of the data being requested. For more information, see the following Remarks section.

### -param pInputData [in]

Caller-supplied pointer to a buffer containing input data.

### -param cbInputData

Caller-supplied size, in bytes, of the buffer pointed to by *pInputData*.

### -param pOutputData [out]

Caller-supplied pointer to a buffer to receive output data.

### -param cbOutputData

Caller-supplied size, in bytes, of the buffer pointed to by *pOutputData*.

### -param pcbOutputNeeded [out]

Caller-supplied pointer to a location to receive the minimum size, in bytes, required for the buffer pointed to by *pOutputData*.

## -returns

If the operation succeeds, this function should return ERROR_SUCCESS. Otherwise, it should return an ERROR_-prefixed Win32 error code. The print monitor UI DLL receives this value in the *pdwStatus* location specified for [XcvData](/previous-versions/ff564255(v=vs.85)).

## -syntax

```cpp
DWORD XcvDataPort(
  _In_  HANDLE  hXcv,
  _In_  LPCWSTR pszDataName,
  _In_  PBYTE   pInputData,
        DWORD   cbInputData,
  _Out_ PBYTE   pOutputData,
        DWORD   cbOutputData,
  _Out_ PDWORD  pcbOutputNeeded
);
```

## -remarks

Port monitor server DLLs are required to define an **XcvDataPort** function so they can receive information from, and return information to, a port monitor UI DLL. The function's address must be included in a [**MONITOR2**](..\winsplp\ns-winsplp-_monitor2.md) structure.

The **XcvDataPort** function is called by the spooler's [XcvData](/previous-versions/ff564255(v=vs.85)) function. The function parameters for **XcvDataPort** and **XcvData** are almost identical. (**XcvData** has an additional parameter, *pdwStatus*, that is not present in **XcvDataPort**.)

The string pointed to by *pszDataName* specifies the operation to be performed. The function must recognize the following data name strings:

| Data Name String | Operation |
|---|---|
| L"AddPort" | All information needed for adding a port has been sent. The function should perform operations necessary to add the specified port, including writing the port name in the registry under the Ports key. The *pInputData* parameter points to a NULL-terminated port name string. If the function returns ERROR_SUCCESS, the spooler marks the port as added. This string is specified by the print monitor UI DLL, from within its [AddPortUI](..\winsplp\nf-winsplp-addportui.md) function. |
| L"DeletePort" | All information needed for deleting a port has been sent. The function should perform operations necessary to delete the specified port, including removing the port name from the registry's Ports key. The *pInputData* parameter points to a NULL-terminated port name string. If the function returns ERROR_SUCCESS, the spooler marks the port as deleted. This string is specified by the print monitor UI DLL, from within its [DeletePortUI](..\winsplp\nf-winsplp-deleteportui.md) function. |
| L"MonitorUI" | The function should use *pOutputData* to return the name of the associated port monitor UI DLL. This string is specified by the print spooler, when an application calls the Microsoft Windows SDK **AddPort** function. |

Typically, the function is written to recognize additional, customized strings that are sent by the UI DLL from within its [AddPortUI](..\winsplp\nf-winsplp-addportui.md), [ConfigurePortUI](..\winsplp\nf-winsplp-configureportui.md), and [DeletePortUI](..\winsplp\nf-winsplp-deleteportui.md) functions. These strings might represent commands that request current configuration values from the server DLL, or that deliver new values. For example, your **XcvDataPort** function might recognize the string "GetTransmissionRetryTimeout", which your UI DLL could send to your server DLL to request the currently stored transmission retry time-out value. Or, you might define a set of strings that must be sent before "AddPort" or "DeletePort" is sent, where the strings are used to supply information identifying the port to add or delete.

For a given *pszDataName* string and input buffer, **XcvDataPort** might first be called with a *cbOutputData* value of zero. The function should return a required buffer size in *pcbOutputNeeded*, along with a return value of ERROR_INSUFFICIENT_BUFFER. The caller can use the value received in *pcbOutputNeeded* to allocate an output buffer of adequate size, and can then call **XcvDataPort** again, this time specifying the allocated buffer size in *cbOutputData*.

The **XcvDataPort** function must validate all input arguments. Specifically, the function must:

- Validate the contents of the string pointed to by the *pszDataName* parameter. If this string represents an administrative operation (typically adding, deleting, or configuring a port), the **XcvDataPort** function should compare the granted access mask that was previously received by the [XcvOpenPort](..\winsplp\nf-winsplp-xcvopenport.md) function with SERVER_ACCESS_ADMINISTER. If the comparison fails, **XcvDataPort** must  return ERROR_ACCESS_DENIED.

- Validate the contents of the buffer pointed to by the *pInputData* parameter. When the spooler calls the **XcvOpenPort** function, it performs no validation on the contents of this buffer. The monitor can make no assumptions about the validity of this data, which can come from a malicious application.

If you are writing a port monitor that will communicate with TCPMON, see [TCPMON Xcv Interface](/windows-hardware/drivers/print/tcpmon-xcv-interface).

## -see-also

[XcvOpenPort](..\winsplp\nf-winsplp-xcvopenport.md)

[DeletePortUI](..\winsplp\nf-winsplp-deleteportui.md)

[ConfigurePortUI](..\winsplp\nf-winsplp-configureportui.md)

[AddPortUI](..\winsplp\nf-winsplp-addportui.md)

[XcvData](/previous-versions/ff564255(v=vs.85))
