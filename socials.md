# Ben's Socials
<div id="socialBlock"></div>

<script>
    // Function to fetch and display social links
    async function displaySocialLinks() {
        try {
            // Fetch the socials.json file
            const response = await fetch('socials.json');
            const data = await response.json();
    
            // Get the socialBlock div
            const socialBlock = document.getElementById('socialBlock');
    
            // Iterate over the key-value pairs in the JSON object
            for (const [key, value] of Object.entries(data)) {
                // Create a text node for the key
                const textNode = document.createTextNode(`${key}: `);
                
                // Create an anchor element for the value
                const anchor = document.createElement('a');
                anchor.href = value;
                anchor.rel = 'me';
                anchor.textContent = value;
    
                // Append the text node and anchor element to the socialBlock div
                socialBlock.appendChild(textNode);
                socialBlock.appendChild(anchor);
    
                // Add a line break for better readability
                socialBlock.appendChild(document.createElement('br'));
            }
        } catch (error) {
            console.error('Error fetching or parsing socials.json:', error);
        }
    }
    
    // Call the function to display social links
    displaySocialLinks();
</script>