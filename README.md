
# useConfirm Custom Hook 

This project demonstrates the usage of a custom React hook called `useConfirm` that triggers a confirmation dialog before executing any action. The hook is flexible, allowing developers to use any modal or confirmation library of their choice.

## Features

- Customizable Confirmation Dialog
- Reusable across different parts of the application
- Callback Integration
- Promise-based API

## Setup

1. Clone the repository:   ```
   git clone <repository-url>
   cd <project-directory>   ```

2. Install dependencies:   ```
   npm install   ```

3. Start the development server:   ```
   npm run dev   ```

## Usage

To use the `useConfirm` hook in your components:

1. Import the hook and the CustomModal component:   ```javascript
   import useConfirm from './hooks/useConfirm';
   import CustomModal from './components/CustomModal';   ```

2. Use the hook in your component:   ```javascript
   const [confirm, ConfirmationDialog] = useConfirm(CustomModal);   ```

3. Create functions that use the `confirm` function:   ```javascript
   const handleSomeAction = async () => {
     try {
       await confirm({
         title: 'Confirm Action',
         message: 'Are you sure you want to perform this action?',
       });
       // Action confirmed, proceed with the action
       console.log('Action confirmed');
     } catch {
       // Action canceled
       console.log('Action canceled');
     }
   };   ```

4. Render the `ConfirmationDialog` component in your JSX:   ```jsx
   return (
     <div>
       {/* Your component JSX */}
       <button onClick={handleSomeAction}>Perform Action</button>
       <ConfirmationDialog />
     </div>
   );   ```

## Example Components

This project includes three example components demonstrating the use of the `useConfirm` hook:

1. **TodoList**: Confirms before deleting a todo item.
2. **UserProfile**: Confirms before updating the user's profile.
3. **Settings**: Confirms before toggling dark mode.

## Customization

You can customize the appearance of the confirmation dialog by modifying the `CustomModal` component in `src/components/CustomModal.jsx`.

## Dark Mode

This project includes a dark mode feature. To toggle dark mode, use the button in the Settings component. The dark mode is implemented using Tailwind CSS classes.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the [MIT License](LICENSE).
