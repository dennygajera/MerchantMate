# MerchantMate


## 1) Folder Structure 

### A typical top-level directory layout

#### 

    ├── ABCProject                  
        ├── UI                                    # Storyboards and Assets
            ├── Login.storyboard
            ├── Home.storyboard
            ├── Settings.storyboard
            ├── Users.storyboard
        ├── Views                                 # Screens/ Views/ Modules
            ├── Login                   
                ├── LoginViewController                    
                ├── LoginViewModel                    
                ├── LoginModel or UserModel                  
            ├── Home                    
                ├── HomeViewController                 
                ├── HomeViewModel                    
                ├── HomeModel               

        ├── Coordinators                          # Navigation Logic
            ├── Coordinator.swift
            ├── AppCoordinator.swift
              
        
        ├── Helpers                               # All Utility/ Helper Classes (ex: Fonts, Extensions, Reusables, etc...)
            ├── Extensions                     
                ├── UIView+Additions                     
                ├── UIView+Additions                   
                ├── UIViewController+Present
            ├── Fonts
                ├── Halvetica
                    ├── Halvetica.ttf
                    ├── Halvetica-Regular.ttf
                Font.swift
                    
                    
        

`Note: Separate views based on Modules, Do not add all designs/ controllers into single storyboard.`

## 2) Style Guide

### Naming Conventions

#### Filenames

All filenames should be camel cased begining in uppercase.

```swift 
✅ DetailViewController.swift
```

```swift 
🚫 detailviewController.swift
```

#### Property Names
```swift 
    UI elements name should be like this loginButton, passwordTextField, titleLabel.
```


#### Extensions

Extensions that add specific functionality to a Type should be suffixed with a brief descriptor of the functionality or addition using a `+` sign as a separator .

```swift 
✅ UIImage+Resizing.swift
```

```swift 
🚫 UIImageExtension.swift
```

Extensions that add multiple smaller general use additions to a Type should be suffixed with `+Additions`.

```swift 
✅ UIImage+Additions.swift
```

```swift 
🚫 UIImageAdditions.swift
```

#### Functions

All functions signatures should be camel cased begining in lowercase.

```swift 
✅ public func myFunction
```

```swift 
🚫 public func myfunction
```

#### Enums

Enums declaractions should be camel cased begining in uppercase, with cases begining in lowercase.

```swift
✅ 

enum MyEnum {
  case firstCase
  case secondCase
  case thirdCase
}
```


```swift
🚫

enum myEnum {
  case firstcase
  case SecondCase
  case Thirdase
}
```

### Access Control

All function, type and variable declarations should be prefixed with an appropriate access control keyword, not only to help your future self, readers and future writers understand intention, but also to restrict access to parts of your code from code in other source files.

```swift 
✅ private func myFunction  
```

```swift 
🚫 func myFunction
```

### Comments

#### Marks

Use `// MARK:` comments to logically group properties and function members throughout the code. Providing a mark description will not only help future readers and writers (including yourself), but will also allow Xcode to interpret and provide bookmarks in the source window’s navigation bar.

```swift
✅

class CaptureViewController: UITableViewController {

  // MARK: Properties (public)

  public var myString: String!

  // MARK: Properties (private)

  private var myStringArray: [String]!

  // MARK: Life cycle 

  override func viewDidLoad() {
      // ...
  }

  override func viewWillAppear(_ animated: Bool) {
      // ...
  }

  // MARK: Actions

  private func buttonWasTapped(_ sender: Any?) {
      // ...
  }
    
```

## 3) Third Party - SPM (Swift Package Manager)
We'll use SPM to integrate third parties until its required (before integreate discuss with Senior developer)
Use native APIs to interect with Network i.e URLRequest/ URLSession.


## 4) Architecture 

#### MVVM-C 

In the MVVM-C (Model-View-ViewModel-Coordinator) architectural pattern, the application is divided into several modules, each serving a specific purpose and following the principles of the MVVM pattern.

#### `Model:`
The Model represents the data and business logic of the application. It encapsulates the data entities, data access, and any other operations related to data manipulation. It should be independent of the View and ViewModel layers.

#### `View:`
The View is responsible for displaying the user interface and handling user interactions. It receives data from the ViewModel to populate the UI and forwards user actions (e.g., button clicks, text input) to the ViewModel for processing.

#### `ViewModel:`
The ViewModel acts as an intermediary between the Model and the View. It contains the presentation logic and exposes data and commands that the View can bind to. It receives data from the Model, processes it, and prepares it for presentation in the View. It also handles user interactions received from the View and communicates with the Model to update the data.

#### `Coordinator:`
The Coordinator is responsible for handling the navigation and flow of the application. It abstracts the navigation logic from the ViewControllers. The Coordinator decides which screens to show based on user actions or application logic and may also manage the presentation of modal views or dialogs.

## 5) Rules

-  Do not use `!` until required, use Optional `?` like this => 
    @IBOutlet var btnFilter : UIButton?
           



