# PlaywrightNetInDocker

## Changes that need to be made in order for the project to work out of the box.

PlaywrightNet.csproj
Add: `<PlaywrightPlatform>Linux</PlaywrightPlatform>`

Inside Program.cs (or appropriate place)
Add and call: 
```
static void PerformInitialPlaywrightInstall()
{
    var exitCode = Microsoft.Playwright.Program.Main(new[] { "install", "--with-deps", "chromium" });
    if (exitCode != 0)
    {
        throw new Exception($"Playwright exited with code {exitCode}");
    }
}
```

Make sure you run headless

Dockerfile is unchanged
