---
UID: NS:winsplp._MONITOR2
title: "_MONITOR2"
author: windows-driver-content
description: The MONITOR2 structure contains pointers to the functions defined by print monitors.
old-location: print\monitor2.htm
old-project: print
ms.assetid: 0bfb5119-2034-4e63-9fbe-e2ff42a352d6
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: spoolfnc_db4ec1e7-1368-4695-bae0-91fd5dcd8a1a.xml, *PMONITOR2, winsplp/PMONITOR2, winsplp/LPMONITOR2, PMONITOR2 structure pointer [Print Devices], MONITOR2 structure [Print Devices], LPMONITOR2, _MONITOR2, *LPMONITOR2, PMONITOR2, winsplp/MONITOR2, MONITOR2, print.monitor2, LPMONITOR2 structure pointer [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: Winsplp.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winsplp.h
apiname:
-	MONITOR2
product: Windows
targetos: Windows
req.typenames: "*PMONITOR2, *LPMONITOR2, MONITOR2"
req.product: Windows 10 or later.
---

# _MONITOR2 structure


## -description


The MONITOR2 structure contains pointers to the functions defined by print monitors.


## -syntax


````
typedef struct _MONITOR2 {
  DWORD cbSize;
  BOOL  (WINAPI *pfnEnumPorts)(
      HANDLE hMonitor, 
      LPWSTR pName, 
      DWORD Level, 
      LPBYTE pPorts, 
      DWORD cbBuf, 
      LPDWORD pcbNeeded, 
      LPDWORD pcReturned);
  BOOL  (WINAPI *pfnOpenPort)(
      HANDLE hMonitor, 
      LPWSTR pName, 
      PHANDLE pHandle);
  BOOL  (WINAPI *pfnOpenPortEx)(
      HANDLE hMonitor, 
      HANDLE hMonitorPort, 
      LPWSTR pPortName, 
      LPWSTR pPrinterName, 
      PHANDLE pHandle, 
      struct _MONITOR2 * pMonitor2);
  BOOL  (WINAPI *pfnStartDocPort)(
      HANDLE hPort, 
      LPWSTR pPrinterName, 
      DWORD JobId, 
      DWORD Level, 
      LPBYTE pDocInfo);
  BOOL  (WINAPI *pfnWritePort)(
      HANDLE hPort, 
      LPBYTE pBuffer, 
      DWORD cbBuf, 
      LPDWORD pcbWritten);
  BOOL  (WINAPI *pfnReadPort)(
      HANDLE hPort, 
      LPBYTE pBuffer, 
      DWORD cbBuffer, 
      LPDWORD pcbRead);
  BOOL  (WINAPI *pfnEndDocPort)(HANDLE hPort);
  BOOL  (WINAPI *pfnClosePort)(HANDLE hPort);
  BOOL  (WINAPI *pfnAddPort)(
      HANDLE hMonitor, 
      LPWSTR pName, 
      HWND hWnd, 
      LPWSTR pMonitorName);
  BOOL  (WINAPI *pfnAddPortEx)(
      HANDLE hMonitor, 
      LPWSTR pName, 
      DWORD Level, 
      LPBYTE lpBuffer, 
      LPWSTR pMonitorName);
  BOOL  (WINAPI *pfnConfigurePort)(
      HANDLE hMonitor, 
      LPWSTR pName, 
      HWND hWnd, 
      LPWSTR pPortName);
  BOOL  (WINAPI *pfnDeletePort)(
      HANDLE hMonitor, 
      LPWSTR pName, 
      HWND hWnd, 
      LPWSTR pPortName);
  BOOL  (WINAPI *pfnGetPrinterDataFromPort)(
      HANDLE hPort, 
      DWORD ControlID, 
      LPWSTR pValueName, 
      LPWSTR lpInBuffer, 
      DWORD cbInBuffer, 
      LPWSTR lpOutBuffer, 
      DWORD cbOutBuffer, 
      LPDWORD lpcbReturned);
  BOOL  (WINAPI *pfnSetPortTimeOuts)(
      HANDLE hPort, 
      LPCOMMTIMEOUTS lpCTO, 
      DWORD reserved);
  BOOL  (WINAPI *pfnXcvOpenPort)(
      HANDLE hMonitor, 
      LPCWSTR pszObject, 
      ACCESS_MASK GrantedAccess, 
      PHANDLE phXcv);
  DWORD (WINAPI *pfnXcvDataPort)(
      HANDLE hXcv, 
      LPCWSTR pszDataName, 
      PBYTE pInputData, 
      DWORD cbInputData, 
      PBYTE pOutputData, 
      DWORD cbOutputData, 
      PDWORD pcbOutputNeeded);
  BOOL  (WINAPI *pfnXcvClosePort)(HANDLE hXcv);
  VOID  (WINAPI *pfnShutdown)(HANDLE hMonitor);
  DWORD (WINAPI *pfnSendRecvBidiDataFromPort)(
      HANDLE hPort, 
      DWORD dwAccessBit, 
      LPCWSTR pAction, 
      PBIDI_REQUEST_CONTAINER pReqData, 
      PBIDI_RESPONSE_CONTAINER* ppResData);
} MONITOR2, *PMONITOR2, *LPMONITOR2;
````


## -struct-fields




### -field cbSize

Specifies the size, in bytes, of the MONITOR2 structure.


### -field pfnEnumPorts

Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff548754">EnumPorts</a> function. (Port monitors only.)


### -field pfnOpenPort

Pointer to the print monitor's <a href="..\winsplp\nf-winsplp-openport.md">OpenPort</a> function.


### -field pfnOpenPortEx

Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff559596">OpenPortEx</a> function. (Language monitors only.)


### -field pfnStartDocPort

Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff562710">StartDocPort</a> function.


### -field pfnWritePort

Pointer to the print monitor's <a href="..\winsplp\nf-winsplp-writeport.md">WritePort</a> function.


### -field pfnReadPort

Pointer to the print monitor's <a href="..\winsplp\nf-winsplp-readport.md">ReadPort</a> function.


### -field pfnEndDocPort

Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff548742">EndDocPort</a> function.


### -field pfnClosePort

Pointer to the print monitor's <a href="..\winsplp\nf-winsplp-closeport.md">ClosePort</a> function.


### -field pfnAddPort

(Obsolete. Must be <b>NULL</b>.) Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff545022">AddPort</a> function.


### -field pfnAddPortEx

(Obsolete. Must be <b>NULL</b>.) Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff545025">AddPortEx</a> function. (Port monitors only.)


### -field pfnConfigurePort

(Obsolete. Must be <b>NULL</b>.) Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff546286">ConfigurePort</a> function.


### -field pfnDeletePort

(Obsolete. Must be <b>NULL</b>.) Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff547427">DeletePort</a> function.


### -field pfnGetPrinterDataFromPort

Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff550506">GetPrinterDataFromPort</a> function.


### -field pfnSetPortTimeOuts

Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff562630">SetPortTimeOuts</a> function. (Port monitors only.)


### -field pfnXcvOpenPort

Pointer to the print monitor's <a href="..\winsplp\nf-winsplp-xcvopenport.md">XcvOpenPort</a> function. (Port monitors only.)


### -field pfnXcvDataPort

Pointer to the print monitor's <a href="..\winsplp\nf-winsplp-xcvdataport.md">XcvDataPort</a> function. (Port monitors only.)


### -field pfnXcvClosePort

Pointer to the print monitor's <a href="..\winsplp\nf-winsplp-xcvcloseport.md">XcvClosePort</a> function. (Port monitors only.)


### -field pfnShutdown

Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/dn926950">Shutdown</a> function.


### -field pfnSendRecvBidiDataFromPort

Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff562071">SendRecvBidiDataFromPort</a> function.


### -field pfnNotifyUsedPorts

 


### -field pfnNotifyUnusedPorts

 


### -field pfnPowerEvent

 



## -remarks


Each language monitor and each port monitor server DLL must provide a MONITOR2 structure. The monitor must supply values for all structure members, and specify the structure's address as the return value for its <a href="..\winsplp\nf-winsplp-initializeprintmonitor2.md">InitializePrintMonitor2</a> function.

If a function is not defined, its pointer must be <b>NULL</b>.



## -see-also

<a href="..\winsplp\nf-winsplp-initializeprintmonitor2.md">InitializePrintMonitor2</a>

<a href="..\winsplp\ns-winsplp-_monitorui.md">MONITORUI</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20MONITOR2 structure%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

