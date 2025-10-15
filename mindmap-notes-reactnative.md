# Mindmap Note

## React Native

- bare or expo - <https://medium.com/@andrew.chester/should-you-use-expo-or-bare-react-native-8dd400f4a468>

react native demo app
using expo
learn how to create a simple app that reads something and saves in the app
bonus: vs code configuration

i want to start a project to help me learn react native. i'll go with the expo option. i want you to write as little code as possible so that i can learn better

- accessing UI elements and states

when i press the button i want to show the text that i wrote on the textbox. it seems strange that the ui elements don't have somekind of id that i can use to do something like textbox.text... can you explain me how it works?

● Great question! This is one of the fundamental differences between React Native (and React in general) and traditional UI programming.

  In React Native, you don't access UI elements directly by ID. Instead, you use state to store data and React automatically updates the UI when the state changes. It's a "declarative" approach - you describe what the UI should look like based on the current state,
  rather than imperatively manipulating elements.

  Here's how it works:

1. State stores your data:

- You use React's useState hook to create a state variable
- This variable holds the text from the input

1. The TextInput is "controlled":

- You give the TextInput a value prop that reads from your state
- You give it an onChangeText prop that updates the state when the user types

1. The Button reads from state:

- When pressed, it just reads the current state value

Try this:

1. Import useState from React at the top: import { useState } from 'react';
2. Inside your HomeScreen function (before the return), create state:
  const [inputText, setInputText] = useState('');
3. Update your TextInput to be "controlled":
  <TextInput
    value={inputText}
    onChangeText={setInputText}
    ... rest of your props
  />
4. Change your Button's onPress to show the state:
  onPress={() => alert(inputText)}

  The key concept: inputText holds the current value, and whenever the user types, onChangeText calls setInputText which updates the state, which causes React to re-render with the new value. Everything flows through state!

  Give it a try and let me know if it clicks or if you have more questions!

- setState

  ok, but where is the setInputValue function?

● Excellent question! This shows you're really thinking about what's happening.

  setInputValue is created by React for you.

  When you call useState(''), React internally:

  1. Creates a state variable with the initial value ''
  2. Generates a setter function specifically for that state
  3. Returns both in an array: [value, setterFunction]

  You don't write the setInputValue function yourself - React creates it and hands it to you. It's part of the React library's magic.

  Behind the scenes (simplified):
  // Inside React's code (not yours):
  function useState(initialValue) {
    let state = initialValue;

    function setState(newValue) {
      state = newValue;
      // React re-renders your component here
    }

    return [state, setState];
  }

  When you call setInputValue('hello'), you're calling that React-generated function, which:

  1. Updates the state value to 'hello'
  2. Tells React "hey, this component's state changed"
  3. React re-renders your component with the new value

  So setInputValue lives inside React's code, not yours. You're just getting a reference to it through useState.

  Does that help clarify it?

- open 8081 in firewall

  nao esquecer de ativar a porta 8081 na firewall

- deploying the application

   it works. but i want it to be saved on my phone, how do i deploy it?

● To create a standalone app that you can install on your phone, you'll need to build an APK (Android Package). With Expo, the easiest way is using EAS Build (Expo Application Services).

  Steps:

1. Install EAS CLI:
npm install -g eas-cli

2. Login to Expo (create a free account if you don't have one):
eas login

3. Configure your project:
cd demo-react-native-app
eas build:configure

4. Build for Android:
eas build --platform android --profile preview

This will:

- Upload your code to Expo's servers
- Build the APK in the cloud (takes 10-20 minutes)
- Give you a download link when done

5. Install on your phone:

- Download the APK from the link
- Open it on your phone
- Allow installation from unknown sources if prompted
- Install and run!

  Note: The free tier has limits on build minutes, but should be plenty for learning.

  Alternative (if you want a quick test): You can also build locally, but it requires more setup (Android Studio, etc.). EAS Build is much simpler.

- credentials stored

when i do eas-login where is the login information stored? i just want to know if i have to take that in consideration so that it doesnt leak into a public repo

● Good security thinking!

  EAS login credentials are stored locally on your machine, NOT in your project directory. They're typically stored in:

- Windows: %USERPROFILE%\.expo or similar
- Mac/Linux: ~/.expo

  So your credentials won't be in your git repo.

  What WILL be added to your project:
  When you run eas build:configure, it will create:
  - eas.json - Build configuration (safe to commit, no secrets)
  - Updates to app.json or app.config.js - App metadata (safe to commit)

  What to watch out for:
  - Never commit API keys, secrets, or environment variables
  - Check your .gitignore includes common secret files like .env

  Let me check what's currently in your .gitignore:

● Read(demo-react-native-app\.gitignore)
  ⎿  Read 44 lines

● Good news! Your .gitignore is already well-configured by Expo. It includes:

- .env*.local (line 34) - environment files with secrets
- .expo/ (line 7) - Expo local data
- *.key,*.jks, etc. (lines 15-19) - signing keys and certificates

  Bottom line: Your EAS login is safe and won't leak into the repo. The Expo template has you covered!
