# Working on task

    > Step 0. Had to fix my local npm first, which was pointing me continuously to a private npm registry ::)

    > Building on top of basic Vue3 project setup, not trying to clean up everything atm to save time

    > Create a default button
        + loading custom font `Inter`
        + std, hover, active, disabled states
        + loading state
        + a button as icon only

    > Button with icon - Plus icon
        > can use reusable\adjustable icons as components vue-tabler-icons
        or font-awesome icons, but neither of those have a perfect `gem\diamond` icon needed, so that one can be done as
        svg, I guess. I think, while working on actual project I would ask a designer to provide me the exact svgs.
        + created slots for left\right icons in Button component
            > using .left\.right class names is safe because styles a "scoped" for this component
        + added v-if check for btn slots
        + changed btn display to flex to add centered vertical alignment for btn children
        > smth is not right with plus btn appearance. Width\height are set to 10px by default, but the icon looks smaller
            Overall I can see difference when I use the exact numbers from Figma template, and when I try to match the design visually.
            That's now visible on the App page, when I compare a 100% scaled screenshot of a designed button and the built one.
            For example I had to increase plus icon dimensions to 17x17px instead of 10x10px to make the icon looking better.
            In this case I would speak to designer and ask if we need the exact pixel numbers or as close as possible visual match to design.
        + don't show plus icon in loading state

[vue-tabler-icons](https://www.npmjs.com/package/vue-tabler-icons)

# ToDo's:

    > crossbrowser testing
    > responsiveness testing
    > optimise base.css resets  
    > use LESS\SASS

    > a button with badge
    > a button with icon and badge
    > icon only + badge
    > a button with a dropdown
    > ghost buttons styling
    > medium buttons styling
    > small buttons styling
    > remove extra comments, console logs, clean up code
    > storybook 
    > component tests
	

