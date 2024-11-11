*This is a submission for the [Open Source AI Challenge with pgai and Ollama ](https://dev.to/challenges/pgai)*

## What I Built | FilmGuru
FilmGuru is an AI movie recommendation engine designed to help you discover the perfect film from a curated database of over 8,000 IMDb movies. Whether you’re in the mood for another mind-bender after watching _Inception_ or just want to try something similar to the last masterpiece you enjoyed, FilmGuru’s got you covered!

### Why FilmGuru?

Ever found yourself scrolling endlessly, unable to decide on your next movie? FilmGuru solves that by understanding what you enjoyed in your last watch and recommending something with a similar vibe. Think of it as your personal movie guru! With FilmGuru, a recommendation isn’t just a list—it’s a hand-picked suggestion designed to turn "meh" into "2 hours of pure bliss." 


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/f8cgdujueg2ikehge1gv.png)

Here’s a sneak peek at a recommendation! With FilmGuru, finding your next favorite film is as easy as pressing play.


## Demo


You can try the app out [here](https://filmguru-omega.vercel.app/)

Thank you for exploring FilmGuru!

## Tools Used


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ih0icp8ku0wyuo4uwy8o.jpeg)

FilmGuru’s journey begins with my movie database, a CSV file sourced from [Kaggle](https://www.kaggle.com/code/payamamanat/imdb-movies/input), containing 8,000 movie records with details like descriptions, year, and other metadata. Here’s how it all comes together:

I started by uploading the CSV to Timescale as a new service, which took just 2 minutes to complete.
Using the SQL editor, I added a primary key column to the table—this is crucial for utilizing Timescale’s pgvector functionality.
I then used pgai with OpenAI’s embedding model (small) to generate embeddings instantly across the entire database, creating a vector representation for each movie entry to allow FilmGuru to find the best matches based on your preferences.

### Behind the Scenes of Your Recommendation Journey

When you enter a prompt (like "I want something like Inception"), it’s sent to the backend server.
The server uses pg AI to create a unique embedding for your query with the help of OpenAI's text-embedding-3-small, transforming it into a vector.
FilmGuru then uses pgvector to search the database for movies with similar embeddings, delivering the closest match as your next recommendation.

It’s seamless, fast, and incredibly fun!


## Final Thoughts
The project came up smooth. I only had one dependency in my back end. That was the pg library for postgres. Kinda cool that I could build the entire backend just with one library.

I’m planning to add an agent that fetches images for each movie, making recommendations even more visually engaging. Stay tuned!


<!-- List all the prize categories (Open-source Models from Ollama, Vectorizer Vibe, All the Extensions) your submission may qualify for, if any. -->
All the Extensions
