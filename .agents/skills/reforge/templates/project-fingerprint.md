# Project Fingerprint

```yaml
project:
  name: ""
  type: mobile | web | desktop | library | cli
  framework: flutter | react_native | expo | android | ios | nextjs | vue | other
  language: dart | kotlin | java | swift | typescript | javascript | other
  framework_version: ""
  language_version: ""

architecture:
  pattern: feature_first | layer_first | clean | mvvm | mvc | redux | other
  state_management: provider | bloc | riverpod | redux | mobx | zustand | context | other
  dependency_injection: get_it | injectable | koin | dagger | hilt | manual | none
  navigation:
    package: go_router | auto_route | navigator_2.0 | react_navigation | other
    pattern: declarative | imperative | hybrid

backend:
  type: rest | graphql | firebase | supabase | custom | none
  base_url: ""
  auth_type: jwt | session | oauth | api_key | none

ui:
  design_system: material | cupertino | custom | hybrid
  theme: material3 | material2 | custom
  dark_mode: supported | not_supported | system_only
  responsive: true | false

testing:
  unit: true | false
  widget: true | false
  integration: true | false
  e2e: true | false
  mocking_library: mockito | mocktail | mocks | none

platforms:
  android: true | false
  ios: true | false
  web: true | false
  desktop: true | false

dependencies:
  total: X
  core: [list of key dependencies]
  dev: [list of key dev dependencies]

ci_cd:
  provider: github_actions | codemagic | bitrise | fastlane | jenkins | none
  stages: [list]

confidence: HIGH | MEDIUM | LOW
notes: ""
```
