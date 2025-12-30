---
name: swiftui-patterns
description: Master SwiftUI with declarative UI, state management, custom views, animations, and modern iOS development patterns.
---

# SwiftUI Patterns

Build modern iOS apps with SwiftUI's declarative syntax, state management, and reactive patterns.

## Core Patterns

### Basic View
```swift
struct ContentView: View {
    @State private var count = 0

    var body: some View {
        VStack {
            Text("Count: \(count)")
                .font(.largeTitle)

            Button("Increment") {
                count += 1
            }
            .buttonStyle(.borderedProminent)
        }
        .padding()
    }
}
```

### ObservableObject
```swift
class UserViewModel: ObservableObject {
    @Published var users: [User] = []
    @Published var isLoading = false

    func fetchUsers() async {
        isLoading = true
        defer { isLoading = false }

        do {
            users = try await UserService.fetchUsers()
        } catch {
            print("Error: \(error)")
        }
    }
}

struct UserListView: View {
    @StateObject private var viewModel = UserViewModel()

    var body: some View {
        List(viewModel.users) { user in
            Text(user.name)
        }
        .task {
            await viewModel.fetchUsers()
        }
    }
}
```

### Custom ViewModifier
```swift
struct CardModifier: ViewModifier {
    func body(content: Content) -> some View {
        content
            .padding()
            .background(Color.white)
            .cornerRadius(10)
            .shadow(radius: 5)
    }
}

extension View {
    func cardStyle() -> some View {
        modifier(CardModifier())
    }
}
```

## Best Practices

1. Use @State for local view state
2. Use @StateObject for view models
3. Use @ObservedObject for passed objects
4. Leverage SwiftUI previews
5. Extract reusable components
6. Use proper property wrappers
7. Implement accessibility

## Resources
- https://developer.apple.com/xcode/swiftui/
