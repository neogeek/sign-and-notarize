# neogeek/sign-and-notarize

## Usage

```yaml
jobs:
  test:
    runs-on: macos-latest
    steps:
      - name: Check out repository
        uses: actions/checkout@v7

      - name: Sign and Notarize
        uses: neogeek/sign-and-notarize@v1.1.2
        with:
          APPLE_ID: ${{ secrets.APPLE_ID }}
          APPLE_APP_PASSWORD: ${{ secrets.APPLE_APP_PASSWORD }}
          APPLE_DEVELOPER_NAME: ${{ secrets.APPLE_DEVELOPER_NAME }}
          APPLE_TEAM_ID: ${{ secrets.APPLE_TEAM_ID }}
          MACOS_CERTIFICATE: ${{ secrets.MACOS_CERTIFICATE }}
          MACOS_CERTIFICATE_PASSWORD: ${{ secrets.MACOS_CERTIFICATE_PASSWORD }}
          MACOS_KEYCHAIN_PASSWORD: ${{ secrets.MACOS_KEYCHAIN_PASSWORD }}
          FRAMEWORK_PATH: "addons/RhythmGameUtilities/libRhythmGameUtilities.macos.template_debug.framework"
```

## Inputs

| Name                         | Description                             | Default Value               | Required |
| :--------------------------- | :-------------------------------------- | :-------------------------- | :------: |
| `APPLE_ID`                   | Users Apple ID                          |                             |    ✅    |
| `APPLE_APP_PASSWORD`         | Users Apple Application Password        |                             |    ✅    |
| `APPLE_DEVELOPER_NAME`       | Users Apple Developer Name              |                             |    ✅    |
| `APPLE_TEAM_ID`              | Users Apple Team ID                     |                             |    ✅    |
| `MACOS_CERTIFICATE`          | MacOS Signing Certificate               |                             |    ✅    |
| `MACOS_CERTIFICATE_PASSWORD` | MacOS Signing Certificate Password      |                             |    ✅    |
| `MACOS_CERTIFICATE_PATH`     | MacOS Signing Certificate Path          | `certificate.p12`           |    -     |
| `MACOS_KEYCHAIN_PASSWORD`    | MacOS Keychain Password                 |                             |    ✅    |
| `MACOS_KEYCHAIN_PATH`        | MacOS Keychain Path                     | `build-signing.keychain-db` |    -     |
| `FRAMEWORK_PATH`             | Path to framework to sign and notarize. |                             |    ✅    |

## Copy MacOS Certificate

```bash
base64 -i Certificate.p12 | pbcopy
```
