import 'dart:html';

import 'package:flutter/material.dart';
import 'package:godwin_new_app/main.dart';

void main() => runApp(MaterialApp(
      debugShowCheckedModeBanner: false,
      home: quoteList(),
    ));

class quoteList extends StatefulWidget {
  @override
  State<quoteList> createState() => _quoteListState();
}

class _quoteListState extends State<quoteList> {
  List<Quote> quotes = [
    Quote(
        author: 'Godwin', text: 'Be yourself; everyone else is already taken'),
    Quote(
        author: 'Godwin', text: 'I have nothing to declare except genius app'),
    Quote(
        author: 'Godwin',
        text: 'The truth is rarely pure and never simple one'),
    Quote(
        author: 'Godwin',
        text: 'I enjoy doing this when ever am with a device'),
  ];
  @override
  Widget build(BuildContext context) {
    return Scaffold(
        backgroundColor: Colors.blue[800],
        appBar: AppBar(
          title: Text('Godwin_App'),
          centerTitle: true,
        ),
        body: Column(
          children: quotes.map(quote) => QuoteCard(quote).toList(),
        ));
  }
}

class QuoteCard extends StatelessWidget {
  final quote;
  final Function delete;
  QuoteCard(this.quote, this.delete);

  @override
  Widget build(BuildContext context) {
    return Card(
        margin: EdgeInsets.fromLTRB(16.0, 16.0, 16.0, 0.0),
        child: Padding(
          padding: const EdgeInsets.all(12.0),
          child: Column(
            crossAxisAlignment: CrossAxisAlignment.stretch,
            children: <Widget>[
              Text(
                quote.text,
                style: TextStyle(
                  fontSize: 20.0,
                  color: Colors.lime[800],
                ),
              ),
              SizedBox(height: 6.0),
              Text(
                quote.author,
                style: TextStyle(
                  fontSize: 15.0,
                  color: Colors.deepPurple,
                ),
              ),
              SizedBox(height: 8.0),
              FlatButton.icon(
                onPressed: () {
                  'delete';
                },
                label: Text('delete quote'),
                icon: Icon(Icons.delete),
              ),
            ],
          ),
        ));
  }
}
