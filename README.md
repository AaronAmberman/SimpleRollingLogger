# SimpleRollingLogger
A simple lightweight logger with rolling log files.

## Breakdown
Logger implements ILogger and has 3 properties...

```C#
/// <summary>Gets or sets the log file.</summary>
public string LogFile { get; set; }

/// <summary>Gets or sets the file size to roll the log file at. If less than 0 then the log file will not be rolled. Default is 102400 (100KB).</summary>
public long LogRollSize { get; set; } = 102400; // 100KB default

/// <summary>Gets or sets the log level for the logger. Default is Trace.</summary>
public LogLevel LogLevel { get; set; } = LogLevel.Trace;
```

It has these methods...

```C#
Debug(string message)
Error(string message)
Fatal(string message)
Info(string message)
RollLogFile()
Trace(string message)
Warning(string message)
```

It is very it to use. Just set the absolute path (including filename) to the LogFile property call the appropriate log method desired.

## Extension
RollLogFile is a part of the interface and marked virtual on the Logger so that you can override its behavior if you so desire. You do not have to call RollLogFile yourself in code. The API will call it when writing to the log file.
