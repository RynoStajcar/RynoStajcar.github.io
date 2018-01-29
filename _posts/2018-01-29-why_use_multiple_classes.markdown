---
layout: post
title:      "Why use multiple Classes"
date:       2018-01-29 21:47:43 +0000
permalink:  why_use_multiple_classes
---


Using multiple classes is a must when it comes to organizing information that needs to be accessed in not just one way. For example the labs primarly use music, there are different genres that contain artists with a variety of songs. You could have one class that holds all the information but there would be no clean way to find out every rap song, or songs made by a particular artist. The attr_accessor/reader/writer is there to assign a method to the object itself and give it attributes. This is helpful when asking the information from the object but you cannot ask that attribute what other objects it applies to because it cannot see that information. So example: song1 = Song.new("Song1", "Rap") and song2 = Song.new("Song2", "Rap"). The genre in both songs is rap but it makes it difficult to make a method that would allow you to ask a genre the songs it contains since rap is not an object. 

This is where using multiple classes comes in, you want to break up the information your going to recieve into chunks you would like to be able to access. Sticking to the example, using a music library you want to seperate the Artist, Genre, Songs, Albums, etc. When you do this you want to keep in mind that you want one class to be the dominate one for taking in the information. Since songs are the most frequently added/changed in music you would just need to make sure Genre and Artists are predefined. Once you have all the artists and genres created, to add a song would be as easy as setting the initialize method to take in three arguments. 
`attr_accessor :name, :genre, :artist

  def initialize(name, genre, artist)
    @name = name
    @genre = genre
    @artist = artist
    genre.add_song(self)
    artist.add_song(self)
  end`
	
	The last two lines of code are what is going to take the song (object) you have just made and add it into a genre and artist class. It will be able it to update the the rap object as well as the artist object you made earlier.
	

  `def initialize("Problems",  rap,  milo)
    @name = "Problems"
    @genre = rap
    @artist = milo
    rap.add_song(#<Song:0x0055673df2c8b8>)
    milo.add_song(#<Song:0x0055673df2c8b8>)
  end`
	
	This makes it easier to read as well as change in the long run, adding new classes for things like albums would only add a new line and argument to this initialize method. 
