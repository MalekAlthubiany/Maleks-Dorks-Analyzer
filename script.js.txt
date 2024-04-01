document.getElementById('urlForm').addEventListener('submit', function(event) {
    event.preventDefault(); // Prevent default form submission

    const url = document.getElementById('urlInput').value;
    const googleDorks = [
        // List of Google dorks options with the name of the purpose of the dork
        // Insert your list of Google dorks options here
    ];

    // Generate HTML for displaying results
    let resultsHTML = '<h2>Google Dorks Results</h2>';
    resultsHTML += '<ul>';
    googleDorks.forEach(dork => {
        resultsHTML += `<li><a href="https://www.google.com/search?q=${encodeURIComponent(`site:${url} ${dork}`)}" target="_blank">${dork}</a></li>`;
    });
    resultsHTML += '</ul>';

    // Display results
    document.getElementById('results').innerHTML = resultsHTML;
});
