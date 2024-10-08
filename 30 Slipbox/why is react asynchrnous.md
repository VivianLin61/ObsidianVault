


React is asynchrnous because **it helps with performance**,
when we call setState it does not update immediately,
the state is updated on the next render,

[[React Loop]]
First is will **collect all the state updates** from the current **trigger**, then react re **renders** the component and generate a second snapshot of what the UI should look like with all the state updates.
After the second snapshot is generated needs to figure out how to update the DOM (Document Object model) so that it matches the second snapshot. 
	In a process known as reconciliation, react figures out what has been changed and then **commits** those changes. 

The reason it works like this because it prevents it from rendering and committing on every state change. This would be very bad for performance. Instead it collects all the state changes and creates a new snapshot from all of those state changes and then calculates the exact updates need and then finally commits those changes to the DOM.
