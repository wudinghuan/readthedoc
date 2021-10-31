![python调用windows api获取电池信息](https://p3-tt.byteimg.com/origin/pgc-image/80c7ed22a06a4bbeb8811c633af2d27f?from=pc)



文件get_battery_status.py

```
import ctypes
from ctypes import Structure, windll
from ctypes.wintypes import (
    DWORD, HICON, HWND, UINT, WCHAR, WORD, BYTE,
    LPCWSTR, INT, LPVOID, HINSTANCE, HMENU, LPARAM,
    WPARAM, HBRUSH, HMODULE, ATOM, BOOL, HANDLE
)


class SYSTEM_POWER_STATUS(Structure):
    _fields_ = [
        ('ACLineStatus', BYTE),
        ('BatteryFlag', BYTE),
        ('BatteryLifePercent', BYTE),
        ('Reserved1', BYTE),
        ('BatteryLifeTime', DWORD),
        ('BatteryFullLifeTime', DWORD),
    ]


GetSystemPowerStatus = windll.kernel32.GetSystemPowerStatus

def battery_status():
    '''
    Implementation of Windows system power status API for plyer.battery.
    '''

    status = SYSTEM_POWER_STATUS()
    if not GetSystemPowerStatus(ctypes.pointer(status)):
        raise Exception('Could not get system power status.')

    return dict(
        (field, getattr(status, field))
        for field, _ in status._fields_
    )
```

main.py

```
import get_battery_status as gbs

a=gbs.battery_status()
print(a['BatteryLifePercent'])
```

把两个py文件放到同一个目录下, 然后运行main.py就行了

![python调用windows api获取电池信息](https://p6-tt.byteimg.com/origin/pgc-image/3a9fd55d4f68450392a4706724279c78?from=pc)